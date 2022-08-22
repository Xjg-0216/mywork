```
.__           .__  .__                               .__       .___
|  |__   ____ |  | |  |   ____   __  _  _____________|  |    __| _/
|  |  \_/ __ \|  | |  |  /  _ \  \ \/ \/ /  _ \_  __ \  |   / __ |
|   Y  \  ___/|  |_|  |_(  <_> )  \     (  <_> )  | \/  |__/ /_/ |
|___|  /\___  >____/____/\____/    \/\_/ \____/|__|  |____/\____ |
     \/     \/                                                  \/
```

# 目录

<!-- MarkdownTOC depth=9 -->

- [1 机器学习基础](#Machinelearning)
- [2 深度学习基础](#Deeplearning)
- [3 目标检测](#Objectdetection)
- [4 语义分割](#Semanticsegmentation)
- [5 实例分割](#Instancesegmentation)
- [6 python基础](#python)
- [7 刷题](#leetcode)
- [8 Git 基础](#Git)
- [9 其他](#other)

```html
                              LWKKKKKKKKEGDEEGDfLEKDLDEEKDGGEKEDKG              
                              ##W#####EKKW####LEKLD#fGKK#EEKDG#WK#.             
                             j####EDW#######W######fLL#LGLG#DGDKWWKt            
                          .###K###G#####KEW###KKKE#LtDKffL##KDGEKK#Wj           
                          #;DG###D####DLGGGED##GED#WtDDLft###KLGGKDEWG          
                          .,KK##EK##KtLKKW#KKD##GD##tDL#;DK#EGfLKK####          
                         ;  K#KE##DLjD####W#W#KfLEK##EDDGW##Et#KE#####t         
                         ; :W#K##KKLKK#####KW#EDDft##KDEE###DfDK#######         
                          fDKD##WfLKW#########KffEtL#KKKK###G#f#EK#####;        
                          D###KKDKKW############fjGtD#K#W#K#K##DEKW####D        
                        t####################KWGfKDKfK#K#G#W###GfL#####K        
                        i####################Wtftj#WDf#K#KfEW#KfjLKK##DD        
                        tE##################W#fLEDEWWKG#EK;DK####K######:       
                         L#K###############WKDWKWKGfLGGGEDtfD#EEKEW##W##        
                       ;W#########W#########Ejtii,,: .:,iGtitG#WKWGK#K#t        
                       :E###WW#############KGL,,:,   .:,iii:;iKDiL#KW##         
                        L#W##########W####KGft;,:.    ..:,,::,fEKDW#E##         
                       f###WW#####KWW#W##EGjti::.     ..:,::::,LW#GDf#L         
                       ##ifDEW##EE#f,,,,;i:::...       ......:,,tKLWW#i         
                      ####DGGG#EK#t:::,,,:::.....     .......::,tGLK##;         
                     DE#DG####WW#G.:::,:......... .    .......::tDfE##.         
                   :#E##EK:jDtWD,.::::,;i;.   ..   .  ........::tKDL#Kf         
                 Df ,W##E ,:,:i:::.:::,,,:.;tj. ... ..........:;L#KK#W;         
                Lf:iW#K##..:.:;,,:::..:,,:...:f, ............:;tE##E##          
               ;L L#######   :i;,::...:,ii;,:.iLi ......:...::ijW##K##          
                i####D##K#Lij:t;,::....:ijEWGG,ift......:...:,tf###W#W          
                   ,#######Kjiii;,:::....,:tfftEfii::::::::.::;W####WD          
                  ;;#W#####E;ti;;,::.....:,,;..fLi;,::::::,;fGK#KW##GE          
                 :.#K######E;ti;;,,:... ..,,;;iit,::::::ijGGGLE#KW#KDj          
                 .;########E;t;;;,,::..  .:,;itt,.,..:jKE#ELtiW#DW#LLi          
                 .##D#W####tit;,;;,::..   ...:...:: .ii,tt:WWK##f#KL;.          
                  KL#WKKK#E;tt;,;;,,:..   ::.....:: :j,:,:tKtLWEG#fL::          
                  GWKL#E##;;tt,,;;,,::.......  .... ,t:,iiGj;LWLWDG,..          
                 ;KWDWjK#Wi;tt,,,;,:::....... ....  ;i::,ij,tLffEjj;            
                D#GGfEW#K,;,tt,,,,,,,::........... .i;:::,,;:;tEiE              
               jKf#tK#K#;,;;it,,,,,,,::....:.:::.. :i;::::,it,GfDj              
              :LK:KKKE#L:,,;it,,,:,:,,::.::::.:::  ,i;:::,ii. GLL;              
               EE:EGW##,,,,,it,,:,:::::::::..:..: .,i,:,,:, jGLLi               
                j#####i,:,,,;t,:,::::::::..  :;.. .,;::,,iEE;;t::               
                 DG##t,,::,,,i,,,::::.:. .... it,..i;:,,i,; .::::               
                  ##f:,,::,,,;;,,,:::.:it  ... ,i.fj,:,it  .  : ,               
                  #L:,,:::,,,,t,,,:::.: iL    ..ifft,,i: .:     i               
                 ,,::::::::,,,tj,,::::.. ,iLj;,:,;;;i,#,        :;              
               ,ii:::::::::,:,;ft,::::....t iDjtttit,tf. .    . :;              
             :ii,::::,:..:::::,ifi,::::...ji::jLLGi,t#E  :    : .,              
          :;;;,::::.,:....::::,,tf,,::....:jt;,iLf;:f#f  :    .  ,              
     :;;;::::...:::..:.:::::.:::,;t;,:......:,tti  ;KK:       . .:              
.:,;;;,::::.........:::....::.:::,tf,:::....::;iiE.DWL.        ::,              
,;;,,,::::..........:.......:::::,tjf;::..:::,,fWiLWtt         ;t               
:,,,,,,,,:.::.:.....:........:.::,iijL::::::,,t#WEGt j         ,i               
......::,,,,::.................::,:,itLGfi,,tDLG:j.Lj,         j:               
.......:::,i,,:....:.............::,;iLLKWEDEDDLGKDtj         :t                
.........:::,;,:::..::............::,ifLDDGLffffLG.;     .    ;.                
:........:::::,,,,:::.. ..........::,ifLGGffjftttf:      ;    ,.                
...... ..:........,,::::......  ...:,,ittttjttitii;ji   .     ..                
.............     ....::..........:::,;ii;itjjttii,;ii .      ::                
.............       ....::........:::,;ittffLffffft;ifj;      t                 
....  ........      ... .:.......::::,;;iiii;;;;;;;iL;iit,    i                 
...   .......    .....   ...........:::.......:::.f,,:,,,,ii;t.                 
 ..  ......       ...     ..........:.........:.:.t,.::::::,,t;   
```

<a name="Machinelearning"></a>

### 1、机器学习基础



<a name="Deeplearning"></a>

### 2、深度学习基础

* [上采样的方式](./深度学习基础/上采样的方式.md)
* [常见的卷积](./深度学习基础/常见的卷积.md)
* [1x1卷积的作用](./深度学习基础/1x1卷积的作用.md)
* [权重初始化方法](./深度学习基础/权重初始化方法.md)
* [normalization](./深度学习基础/normalization.md)

* [激活函数的选取](./深度学习基础/激活函数的选取.md)
* [优化器的选取](./深度学习基础/优化器的选取.md)
* [反向传播推导](./深度学习基础/反向传播推导.md)
* [解决过拟合问题](./深度学习基础/解决过拟合问题.md)
* [评价指标](./深度学习基础/评价指标.md)
* [混合精度训练](./深度学习基础/混合精度训练.md)

<a name="Objectdetection"></a>

### 3、目标检测：

* [YOLO系列总结](./目标检测/YOLO系列.md)

* [面试常问](./目标检测/目标检测常见问题.md)

* [项目](./项目/项目_雷达和光学空天遮挡目标识别.md)

  * [遮挡目标检测](./项目/遮挡目标检测.md)
  * [遮挡目标程序](./项目/遮挡程序.md)
  * [火箭军比赛](./项目/火箭军比赛.md)

* [SSD](./目标检测/SSD.md)

* [RetinaNet](./目标检测/RetinaNet.md)

* **Anchor-free**

  [FCOS](./目标检测/FCOS.md)
  
  [YOLOX](./目标检测/yolox.md)

<a name="Semanticsegmentation"></a>

### 4、语义分割：

* [FCN](./语义分割/FCN.md)

<a name="Instancesegmentation"></a>

### 5、实例分割：

* [Mask RCNN](./实例分割/MaskRCNN.md)

<a name="python"></a>

### 6、Python基础

* [ACM模式下输入输出](./ACM模式下输入输出.md)

* [排序](./代码/排序.md)
* [python基础](./代码/python数据类型.md)
* [常见Linux命令](./代码/常见Linux命令.md)
* [numpy](./代码/numpy.md)
* [torch](./代码/torch.md)
* [模型定义](./代码/模型定义.md)
* [损失函数](./代码/损失函数.md)
* [读取存储](./代码/cv2.md)

<a name="leetcode"></a>

### 7、刷题

* [链表构造](./代码/链表输入.md)
* [二叉树构造](./代码/二叉树输入.md)
* [数组](./代码/数组.md)
* [链表](./代码/链表.md)
* [哈希表](./代码/哈希表.md)
* [字符串](./代码/字符串.md)
* [双指针法](./代码/双指针法.md)
* [栈与队列](./代码/栈与队列.md)
* [二叉树](./代码/二叉树.md)
* [回溯算法](./代码/回溯算法.md)
* [贪心算法](./代码/贪心算法.md)
* [动态规划](./代码/动态规划.md)
* [单调栈 ](./代码/单调栈.md)

<a name="Git"></a>

### 8、Git基础

* [git基础](./git基础/git教程.md)

<a name="other"></a>

### 9、其他

* 字符画
  * [文字转字符画](http://patorjk.com/software/taag/)
  * [图片转字符画](http://www.degraeve.com/img2txt.php)
* [markdown常用数字符号](https://www.jianshu.com/p/86d4e3502e46)

