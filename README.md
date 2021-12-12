# Mask2Former: Masked-attention Mask Transformer for Universal Image Segmentation

This model is the 2nd selected model to compare with the model of our chosen paper. They use different optimization techniques to the CNN. We aim to compare their performance using same dataset and pretrained models.


## Run the following setup first:
### Example conda environment setup
```bash
conda create --name mask2former python=3.8 -y
conda activate mask2former
pip install torch torchvision torchaudio
pip install -U opencv-python

# under your working directory
git clone https://github.com/facebookresearch/detectron2
cd detectron2
pip install -e .
pip install git+https://github.com/cocodataset/panopticapi.git
pip install git+https://github.com/mcordts/cityscapesScripts.git

cd ..
git clone git@github.com:facebookresearch/Mask2Former.git
cd Mask2Former
pip install -r requirements.txt
cd mask2former/modeling/pixel_decoder/ops
sh make.sh
```

## Run the pretrained model to test:

1. Pick a model and its config file from
  [model zoo](MODEL_ZOO.md),
  for example, `configs/cityscapes/panoptic-segmentation/maskformer2_R101_bs16_90k.yaml`.
2. There is `demo.py` that is able to demo builtin configs. Run it with:
```
cd demo/
python demo.py --config-file ../configs/cityscapes/panoptic-segmentation/maskformer2_R101_bs16_90k.yaml \
  --input input1.jpg input2.jpg \
  [--other-options]
  --opts MODEL.WEIGHTS /path/to/checkpoint_file
```


## We keep the license of the original ReadMe file
## License

Shield: [![CC BY-NC 4.0][cc-by-nc-shield]][cc-by-nc]

The majority of Mask2Former is licensed under a
[Creative Commons Attribution-NonCommercial 4.0 International License](LICENSE).

[![CC BY-NC 4.0][cc-by-nc-image]][cc-by-nc]

[cc-by-nc]: http://creativecommons.org/licenses/by-nc/4.0/
[cc-by-nc-image]: https://licensebuttons.net/l/by-nc/4.0/88x31.png
[cc-by-nc-shield]: https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg


However portions of the project are available under separate license terms: Swin-Transformer-Semantic-Segmentation is licensed under the [MIT license](https://github.com/SwinTransformer/Swin-Transformer-Semantic-Segmentation/blob/main/LICENSE), Deformable-DETR is licensed under the [Apache-2.0 License](https://github.com/fundamentalvision/Deformable-DETR/blob/main/LICENSE).

## <a name="CitingMask2Former"></a>Citing Mask2Former

If you use Mask2Former in your research or wish to refer to the baseline results published in the [Model Zoo](MODEL_ZOO.md), please use the following BibTeX entry.

```BibTeX
@article{cheng2021mask2former,
  title={Masked-attention Mask Transformer for Universal Image Segmentation},
  author={Bowen Cheng and Ishan Misra and Alexander G. Schwing and Alexander Kirillov and Rohit Girdhar},
  journal={arXiv},
  year={2021}
}
```

If you find the code useful, please also consider the following BibTeX entry.

```BibTeX
@inproceedings{cheng2021maskformer,
  title={Per-Pixel Classification is Not All You Need for Semantic Segmentation},
  author={Bowen Cheng and Alexander G. Schwing and Alexander Kirillov},
  journal={NeurIPS},
  year={2021}
}
```

## Acknowledgement

Code is largely based on MaskFormer (https://github.com/facebookresearch/MaskFormer).
