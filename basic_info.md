# basic information about lung nodule 

## mhd file
mhd文件中使用
GetOrigin获取的是体素空间定义的原点，
GetSpacing获取的是“世界空间”中相邻单位体素的间距

1. image position(0020,0032): specifies the x,y, and z coordinates of the upper left hand corner of the image. In other words, this tag specifies the coordinates of the first voxel transmitted.

图像位置：指示了图像左上角的第一个像素的空间坐标（x,y,z），也就是DICOM文件传输的第一个像素的坐标。
http://blog.csdn.net/inter_peng/article/details/22822237

