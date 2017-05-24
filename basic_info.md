# basic information about lung nodule 

## mhd file
mhd文件中使用
GetOrigin获取的是体素空间定义的原点，
GetSpacing获取的是“世界空间”中相邻单位体素的间距

#### image position
specifies the x,y, and z coordinates of the upper left hand corner of the image. In other words, this tag specifies the coordinates of the first voxel transmitted.

图像位置：指示了图像左上角的第一个像素的空间坐标（x,y,z），也就是DICOM文件传输的第一个像素的坐标。
http://blog.csdn.net/inter_peng/article/details/22822237


### SliceThickness和SliceLocation的关系 
当只读入一张图像时，层厚用SliceThickness；当读入多张图像时，层厚用首两张图像的SliceLocation之差表示。

### CT值从-1024开始的。

### RescaleIntercept
用于得到输出灰度值，也就是每个像素的PixelData值加上RescaleIntercept得到的结果。如一张图像上一个像素点灰度为1024，偏移DCM_RescaleIntercept=-1024，那么该像素对应输出1024+（-1024）=0；


### CT值怎么和matlab中图像的灰度值联系起来

用从DICOM文件中读取的rescaleslope值和rescale intercept值可以将每个像素的灰度值转换成CT值。
metadata=dicominfo ('***.dcm')
Hu=pixel_val*rescale_slope+rescale_intercept;
pixel_val是第i个像素的灰度值
Hu是第i个像素的CT值
