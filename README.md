# yolov5_face_landmark  
## 基于yolov5的人脸检测，带关键点检测  
> 代码说明：  
+ 1，在yolov5的检测基础上，加上关键点回归分支，请先下载yolov5的工程：https://github.com/ultralytics/yolov5  
+ 2，detect_one.py是单张图片的测试代码，　基于部分wideface训练的模型，稍后在百度云公开。  
>> 主要修改代码部分：    
+ (1)hyp.scatch.yaml中增加关键点loss的超参数（landmark: 0.5）  
+ (2)yolo.py中增加了关键点回归的计算  
+ (3)face_datasets.py为人脸数据的读取方式，准备数据的格式参考yolov5的格式，在后面增加关键点的坐标（归一化）  
+ (4)　loss.py中增加关键点回归的loss计算  
+ (5) 链接: https://pan.baidu.com/s/1zjPIF2NZ9CGtB2iUCox6hw  密码: j83n  
+ (6) 效果图 :   ![效果图](https://github.com/xialuxi/yolov5_face_landmark/blob/main/test_yolov5.jpg)  
> 关于口罩人脸的问题：
+ 1，增加口罩人脸这个类别，建议不要直接在检测分支中增加类别。
+ 2，应该在关键点分支额外增加一个属性分支，接一个二分类，判断有没有戴口罩。
+ 3，这样可以减少口罩人脸的误检问题
