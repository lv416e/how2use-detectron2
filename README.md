# how2use-detectron2
Overview of Detectron2 usage

---
# Training and Evaluation
## Faster R-CNN +FPN with ResNet-50

```python
python tools/train_net.py --num-gpus 2 --config-file configs/COCO-Detection/faster_rcnn_R_50_FPN_1x.yaml
```

---
# Evaluation only

```python
python tools/train_net.py \
--num-gpus 2 --eval-only \
--config-file output/config.yaml \
MODEL.WEIGHTS output/directory/for/trained/model/foofarfoo.pth
```

---
# Annotation visualization

```python
python tools/visualize_data.py \
--source annotation \
--config-file configs/COCO-Detection/faster_rcnn_R_50_FPN_1x.yaml \
--output-dir output/directory/for/annotated/images/
```

---
# Inference result visualization

```python
python tools/visualize_json_results.py \
--input output/directory/for/inference/coco_instances_results.json \
--output output/directory/for/predicted/images --dataset foofarfoo_train
```

---
# Demo (Image, Video, Webcam)
## Images

```python
python demo/demo.py \
--config-file path/to/config/file/config.yaml \
--confidence-threshold 0.5 \
--input path/to/image/raw_image.jpg \
--output output/directory/for/predicted/images/predicted_image.jpg \
--opts MODEL.WEIGHTS output/directory/for/trained/model/foofarfoo.pth
```

## Video

```python
python demo/demo.py \
--config-file path/to/config/file/config.yaml \
--video-input path/to/movie/raw_movie.mp4 \
--confidence-threshold 0.5 \
--output output/directory/for/predicted/movies/predicted_movie.mp4 \
--opts MODEL.WEIGHTS output/directory/for/trained/model/foofarfoo.pth
```

## Webcam

```python
python demo/demo.py \
--config-file path/to/config/file/config.yaml \
--webcam \
--confidence-threshold 0.5 \
--output output/directory/for/predicted/movies/predicted_movie.mp4 \
--opts MODEL.WEIGHTS output/directory/for/trained/model/foofarfoo.pth
```


