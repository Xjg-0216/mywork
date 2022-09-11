### pytorch加载数据



自定义数据集

```python
from torch.utils.data import Dataset
from PIL import Image 
class MyDataset(Dataset):
    def __init__(self, images_path:list, images_class:list, transform=None):
        self.images_path = images_path
        self.images_path = images_class
        self.transform = transform
    def __len__(self):
        return len(self.images_path)
    def __getitem__(self, item):
        img = Img.open(self.images_path[item])
        label = self.images_class[item]
        if self.transform is not None:
            img = self.transform(img)
        return img, label
    @staticmethod
    def collate_fn(batch):
        images, labels = tuple(zip(*batch))
        images = torch.stack(images, dim=0)
        labels = torch.as_tensor(labels)
        return images, labels

device = torch.device("cuda" if torch.cuda.is_available() else "cpu")
data_transform = {
    "train": transforms.Compose([transforms.RandomResizedCrop(224), 
                                transforms.RandomHorizontalFlip(), 
                                transforms.ToTensor(),
                                transforms.Normalize([0.485, 0.456, 0.406], [0.229, 0.224, 0.225])]), 
    "val": transforms.Compose([transforms.Resize(256), 
                              transforms.CenterCrop(224), 
                              transforms.Totensor(), 
                              transforms.Normalize([0.485, 0.456, 0.406], [0.229, 0.224, 0.225])])
}
train_data_set = MyDataset(images_path=train_images_path,
                          images_class=train_images_label, 
                          transform=data_transform["train"])
batch_size = 8
nw = min([os.cpu_count(), batch_size if batch_size > 1 else 0, 8]) # number of workers
train_loader = torch.utils.data.DataLoader(train_data_set, 
                                          batch_size=batch_size,
                                          shuffle=True,
                                          num_workers=nw,
                                          collate_fn=train_data_set.collate_fn)
for step, data in enumerate(train_loader):
    images, labels = data

```

