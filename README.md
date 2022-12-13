# BlindWaterMark

盲水印 by python


### install

```bash
pip install -r requirements.txt
```


### 文件说明

* bwm.py            (python2用这个)
* bwmforpy3.py      (python3用这个)
* hui.png           (无水印的原图)
* wm.png            (水印图)
* hui_with_wm.png   (有盲水印的图)
* wm_from_hui.png   (反解出来的水印图)


### 使用

* 合成盲水印图

    # python bwmforpy3.py encode 无水印原图.png 水印图.png 有盲水印的图.png
    python bwmforpy3.py encode hui.png wm.png hui_with_wm.png



* 提取图中的盲水印 (需要原图)

    # python bwmforpy3.py decode 无水印原图.png 有盲水印的图.png 水印图.png
    python bwmforpy3.py decode hui.png hui_with_wm.png wm_from_hui.png


### Usage

注意程序python2和python3版本的加解密结果会有所不同，主要原因是python2和python3 random的算法不同，如果要让python3兼容python2的random算法请加 --oldseed参数。


    Usage: python bwm.py <cmd> [arg...] [opts...]
      cmds:
        encode <image> <watermark> <image(encoded)>
               无水印原图 + 水印图 -> 有盲水印的图
        decode <image> <image(encoded)> <watermark>
               无水印原图 + 有盲水印的图 -> 水印图
      opts:
        --debug,          Show debug
        --seed <int>,     Manual setting random seed (default is 20160930)
        --oldseed         For python3 to use python2 random algorithm.
        --alpha <float>,  Manual setting alpha (default is 3.0)

