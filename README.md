# UIT Car Racing 2023
## Car
Sử dụng để chạy mô hình YOLOv5 và Segmentation trên Jetson Nano
### Car Structure
```
car
│   reset_cam.sh                  #Reset camera
│   run.py        
│
├───export
│       onnx2trt.py
│       torch2torchscript.py
│
├───images                         #Test images                      
│   ├───detect
│   │       bus.jpg
│   │       zidane.jpg
│   │
│   └───segment
│           980.jpg
│           982.jpg
│
├───lib                            #Library
│   ├───cfg
│   │       cfg.yaml               #Configuration
│   │
│   ├───control
│   │       UITCar.py
│   │
│   ├───model
│   │       trt.py
│   │       unet.py
│   │
│   └───utils
│           plots.py
│           utils.py
│
├───runs
├───tools
│       test_cam.py
│       test_torchscript.py
│       test_trt.py
│
└───weights                         #Pretrain
```
### Export model
ONNX to TRT:
```
python3 export/onnx2trt.py --onnx best_obj.onnx --engine best_obj.engine
```
Torchscript:
```
python3 export/torch2torchscript.py --weight best_seg.pt
```

### Demo Test
```
├───tools
│       test_cam.py                 
│       test_torchscript.py
│       test_trt.py
```
#### Test Segmentation model
```
python3 tools/test_torchscript.py
```
#### Test YOLOv5n model
```
python3 tools/test_trt.py
```
#### Test camera
```
python3 tools/test_cam.py
```

## Training Model
Run in Colab to training model with custom datasets
