



#  一、参考资料

https://zhuanlan.zhihu.com/p/96122311




# 二、 模型转换


## 2.1、darknet --> bin 文件



/media/jcq/Soft/OpenVino/Model/tensorflow-yolo-v3

source activate tensorflow-gpu

export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda-10.0/lib64
export PATH=$PATH:/usr/local/cuda-10.0/bin
export CUDA_HOME=$CUDA_HOME:/usr/local/cuda-10.0




python3 mo_tf.py \
--input_model /media/jcq/Soft/OpenVino/WorkSpace/yolov3-tiny/model/frozen_tiny_yolo_v3.pb \
--batch 1
--tensorflow_use_custom_operations_config /media/jcq/Soft/OpenVino/source/openvino-master/model-optimizer/extensions/front/tf/yolo_v3_tiny.json


> ok ,能够运行成功，下载进行测试即可


[ SUCCESS ] Generated IR version 10 model.
[ SUCCESS ] XML file: /media/jcq/Soft/OpenVino/intel/openvino_2020.4.287/deployment_tools/model_optimizer/./frozen_tiny_yolo_v3.xml
[ SUCCESS ] BIN file: /media/jcq/Soft/OpenVino/intel/openvino_2020.4.287/deployment_tools/model_optimizer/./frozen_tiny_yolo_v3.bin
[ SUCCESS ] Total execution time: 6.05 seconds.
[ SUCCESS ] Memory consumed: 525 MB.




# 三、模型测试

## 3.1、测试文件

python 运行：

python3 object_detection_demo_yolov3_async.py -m /media/jcq/Soft/OpenVino/WorkSpace/yolov3-tiny/model/frozen_tiny_yolo_v3.xml -i /home/mai/test.mp4

python3 object_detection_demo_yolov3_async.py -m /media/jcq/Soft/OpenVino/WorkSpace/yolov3-tiny/model/frozen_tiny_yolo_v3.xml -i cam



cpp 运行：



## 3.2、 openvino 环境检测


(√)

./hello_classification \
/media/jcq/Soft/OpenVino/open_model_zoo/tools/accuracy_checker/data/test_models/SampLeNet.xml \
/media/jcq/Soft/OpenVino/intel/openvino_2020.4.287/deployment_tools/demo/car_1.bmp \
CPU









# 四、






























