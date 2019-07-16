# 应用"baidumap"包批量转换地理名称至经纬度

-----

感谢大神badbye写的适用于R的百度地图扩展包，github地址：https://github.com/badbye/baidumap

-----

 

```R
#安装baidumap包
library(devtools)
install_github('badbye/baidumap')
#设置当前工作路径
getwd()
setwd("C:/Users/optif/Desktop")
#加载地址数据
add <- read.table('address_list.txt',header = F, col.names=c('address'),as.is = c(1))
View(add)
add <- add$address   #转化为向量格式，备for循环使用
head(add)
#加载baidumap包
library(baidumap)
#设置百度API，需要自己申请，示例为CSDN用户rockllee共享的API
options(baidumap.key='nSxiPohfziUaCuONe4ViUP2N')
#开始转换
shuchu<- getCoordinate(add, formatted = T)
#输出为CSV文件
write.csv(shuchu,"shuchu.csv")
```

