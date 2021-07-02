



#  一、参考资料

https://zhuanlan.zhihu.com/p/96122311




# 二、 模型转换


## 2.1、darknet --> bin 文件




python3 convert_weights_pb.py 
--class_names voc.names 
--weights_file yolov3_tiny_200000.weights
--data_format NHWC 
--tiny --output_graph frozen_tiny_yolo_v3.pb






python mo_tf.py --input_model frozen_darknet_yolov3_model.pb 
--tensorflow_use_custom_operations_config yolo_v3_tiny.json 
--input_shape=[1,416,416,3]  --data_type=FP32




/media/jcq/Soft/OpenVino/Model/tensorflow-yolo-v3


python3 /media/jcq/Soft/OpenVino/Model/tensorflow-yolo-v3/convert_weights_pb.py \
--class_names /media/jcq/Soft/OpenVino/Model/tensorflow-yolo-v3/data/coco.names \
--weights_file /media/jcq/BACKUP/Darknet/toos/darknet2onnx/weights/yolov3-tiny.weights \
--data_format NHWC \
--tiny --output_graph /media/jcq/Soft/OpenVino/Model/tensorflow-yolo-v3/saved_model/frozen_tiny_yolo_v3.pb


source activate tensorflow-gpu

export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda-10.0/lib64
export PATH=$PATH:/usr/local/cuda-10.0/bin
export CUDA_HOME=$CUDA_HOME:/usr/local/cuda-10.0

