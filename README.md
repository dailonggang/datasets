# datasets
现在前沿的目标检测算法（如Faster R-CNN, Yolo, SSD, Mask R-CNN等）基本都是在这些常规数据集上实验的，但是在航空遥感图像上的检测效果并不好，对于航空遥感图像目标检测任务，常规数据集往往难以训练出理想的目标检测器，需要专门的航空遥感图像数据库。主要原因是航空遥感图像有其特殊性：

  *尺度多样性：航空遥感图像从几百米到近万米的拍摄高度都有，且地面目标即使是同类目标也大小不一，如港口的轮船大的有300多米，小的也只有数十米；
 
  *视角特殊性：航空遥感图像的视角基本都是高空俯视，但常规数据集大部分还是地面水平视角，所以同一目标的模式是不同的，在常规数据集上训练的很好的检测器，使用在航空遥感图像上可能效果很差；

  *小目标问题：航空遥感图像的目标很多都是小目标（几十个甚至几个像素），这就导致目标信息量不大，基于CNN的目标检测方法在常规目标检测数据集上一骑绝尘，但对于小目标，CNN的Pooling层会让信息量进一步减少，一个24*24的目标经过4层pooling后只有约1个像素，使得维度过低难以区分出来；

  *多方向问题：航空遥感图像采用俯视拍摄，目标的方向都是不确定的（而常规数据集上往往有一定的确定性，如行人、车辆基本都是立着的），目标检测器需要对方向具有鲁棒性；

  *背景复杂度高：航空遥感图像视野比较大（通常有数平方公里的覆盖范围），视野中可能包含各种各样的背景，会对目标检测产生较强的干扰。

1.DOTA：A Large-scale Dataset for Object Detection in Aerial Images。这是武大遥感国重实验室夏桂松和华科电信学院白翔联合做的一个数据集，2806张遥感图像（大小约4000*4000），188,282个instances，分为15个类别。样本类别及数目如下（与另一个开放数据集NWPU VHR-10对比）。

链接：http://captain.whu.edu.cn/DOTAweb/

2.UCAS-AOD：Dataset of Object Detection in Aerial Images，中科大模式识别实验室标注的，只包含两类目标：汽车，飞机，以及背景负样本。

链接：http://www.ucassdl.cn/resource.asp

DownLoad：Dataset 及其基本情况概述Instruction Instruction-cn 

References:[1]H. Zhu, X. Chen, W. Dai, K. Fu, Q. Ye, J. Jiao, "Orientation Robust Object Detection in Aerial Images Using Deep Convolutional Neural Network," IEEE Int'l Conf. Image Processing, 2015.

3.NWPU VHR-10：西北工业大学标注的航天遥感目标检测数据集，共有800张图像，其中包含目标的650张，背景图像150张，目标包括：飞机、舰船、油罐、棒球场、网球场、篮球场、田径场、港口、桥梁、车辆10个类别。开放下载，大概73M。

链接：http://jiong.tea.ac.cn/people/JunweiHan/NWPUVHR10dataset.html

4.RSOD-Dataset：武汉大学团队标注，包含飞机、操场、立交桥、 油桶四类目标，数目分别为：

飞机：4993 aircrafts in 446 images. 

操场： 191 playgrounds in 189 images. 

立交桥： 180 overpass in 176 overpass.

油桶：1586 oiltanks in 165 images.

链接：https://github.com/RSIA-LIESMARS-WHU/RSOD-Dataset-

5.INRIA aerial image dataset：Inria是法国国家信息与自动化研究所简称，该机构拥有大量数据库，其中此数据库是一个城市建筑物检测的数据库，标记只有building, not building两种，且是像素级别，用于语义分割。训练集和数据集采集自不同的城市遥感图像。

链接：https://project.inria.fr/aerialimagelabeling/

6.TGRS-HRRSD-Dataset：HRRSD是中国科学院西安光学精密机械研究所光学影像分析与学习中心制作用于研究高分辨率遥感图像目标检测的数据集。

链接：https://github.com/CrazyStoneonRoad/TGRS-HRRSD-Dataset
