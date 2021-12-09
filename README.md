# 武汉大学引力波天文学课程材料

 - PPT: [坚果云链接](https://www.jianguoyun.com/p/DYUm4V4Qwt6lBhj1oKAE)
 - 讲义：[overleaf链接](https://www.overleaf.com/read/ckcdfzcmbmyk) (理想情况下我希望可以为本课程特别写一个讲义，但最近有点忙……所以目前请参考我的博士论文的1.2节吧：[链接](https://repository.lib.cuhk.edu.hk/en/islandora/object/cuhk%3A2399031/metadata) :-）（12月9日更：搞定了！竟然真的写成了一个小讲义！）
 - 课前要求：（1) 请阅读发现引力波的第一篇论文：[杂志链接](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.116.061102)， [arxiv链接](https://arxiv.org/abs/1602.03837) （2)上课时请携带笔记本电脑，因为第二课时我打算一起阅读代码，在自己的电脑上应能看得更清楚
 - 课程安排：共两课时，每课时〜45分钟，第一课时：贝叶斯参数估计，高斯稳定噪音的致密双星并合引力波信号似然函数推导，几个引力波事件的参数估计例子，用引力波检验广义相对论（简要介绍我最近的一篇检验引力波宇称对称的论文[链接](https://arxiv.org/abs/2109.09718)）；第二课时：介绍`PyCBC_Inference`的使用，一起阅读`PyCBC`的源代码，用Jupyter notebook跑一个例子。

## 用PyCBC进行参数估计
安装PyCBC:
 
 ```
pip install pycbc
```

用Pycbc_inference估计GW150914的参数：

 ```
pycbc_inference --verbose \
    --seed 19930309 \
    --config-file inference-gw150914_095045.ini \
    --output-file result.hdf \
    --nprocesses 128 \
    --force
```

我已经运行过以上代码，在大量并行的计算条件下，花费了几个小时，得到如下结果：[链接](https://www.atlas.aei.uni-hannover.de/work/yifan.wang/projects/whu/imrpv2/run_output/html/)。在`1-inference_GW150914.ipynb`中我们分析一下这个参数估计的结果，运行结果文件我放在[这里](https://www.atlas.aei.uni-hannover.de/work/yifan.wang/projects/whu/imrpv2/run_output/posterior_files/H1L1V1-EXTRACT_POSTERIOR_GW150914-1126259200-400.hdf)
