# verify_code

2018.2.4
1.说明

a.验证码识别的第一步在分割，一次性用cnn识别4个要求的数据量非常大，如果能很好的分割开单个的验证码， 那识别单个的字母或者数字要容易。
b.目前我所知的分割的方法有“滴水算法”，但是从论文中来看，识别效果并不很好，而且对图片的前期处理较多。
c.本项目旨在用BP来实现4字符验证码图片分割（同理可推广至多字符）。

2.结构说明
--Feasibility
  --data                ## 数据存放
    --ori
    *三十张原始数据*     ## 小样本表现良好（BP的优势）
    --train             ## 训练集，手动标注好的红线为分割线
    *训练集*             
    --validate
    *验证集*
    *train.txt*
    *validate.txt*
  --fix_model
  *训练好的ckpt模型*    ## 保存模型， 训练约3万epoch
  --model
    --result          ##  识别结果，目测还行，后面再在MNIST上做fine tune,
    *model.py*        ## 模型源码
    *my_run.py*       ## 验证
--Pub                 ## 共用文件
  *file.py*

后期工作：（有时间情况下：））
1.尝试SVM+HOG、BP、cnn识别单个字符，有做好的小朋友希望分享下~~；
2.优化模型，识别，提高识别速度。
