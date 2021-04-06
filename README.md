# Dynamic Transfer for Multi-Source Domain Adaptation (CVPR 2021)
A [pytorch](http://pytorch.org/) implementation of [DRT](https://arxiv.org/abs/2103.10583).
If you use this code in your research please consider citing
>@article{li2021dynamic,
  title={Dynamic Transfer for Multi-Source Domain Adaptation},
  author={Li, Yunsheng and Yuan, Lu and Chen, Yinpeng and Wang, Pei and Vasconcelos, Nuno},
  journal={arXiv preprint arXiv:2103.10583},
  year={2021}
}
### Requirements

- Hardware: PC with Tesla-V100.
- Software: *CUDA >= 10.0*, *Anaconda3*, *pytorch >= 1.0.0*

### Download Dataset

- [DomainNet](http://ai.bu.edu/M3SDA/)
- [Label](http://)

Please merge the dataset and the label into the same folder

### Evaluate DRT

The pre-trained models are provided- [Clipart](https://drive.google.com/file/d/1mh1jpUWQrginSACZvZDmtyYeh-TZUxBS/view?usp=sharing), [Infograph](https://drive.google.com/file/d/16zmGRRnXwsTMgj2-RKhwWdaOLXkozXMl/view?usp=sharing), [Painting](https://drive.google.com/file/d/15YhOjPjuutHrcK-m511OERu_4vIVYArD/view?usp=sharing), [Quickdraw](https://drive.google.com/file/d/1O4JwTDudqT1aj2VfFxgU1ld7bk0Hlcth/view?usp=sharing), [Real](https://drive.google.com/file/d/1ygMj4nJU74qywMbdq2DvQyyZZHngBD-3/view?usp=sharing), [Sketch](...). Here we use 'Clipart' as an example. If you want to test other domains, all you need to do is just to replace the name of the dataset.

```
python drt.py --batch-size 64 --num-layer 2 --save /path/to/output --src_path clipart_comb.txt --trg_path clipart_train.txt --val_path clipart_test.txt --root /path/to/dataset --weight /paht/to/model --evaluate
```

### Train DRT

Please download the ImageNet pre-trained [dynamic model](...). Again we use 'Clipart' as an example. For training DRT with other domains, you can use other scripts in the folder [DRT/script](https://github.com/liyunsheng13/DRT/tree/main/script).

```
sh clipart_train.sh /path/to/output /path/to/dataset /path/to/resnet_dy_pretrained.pth
```
