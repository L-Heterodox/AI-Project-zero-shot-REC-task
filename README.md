# 零样本下的指代表达理解任务
## 1 代码使用说明
### 1.1 环境配置及准备工作
- 将该项目克隆到本地
- 环境配置：采用pytorch框架，按照requirement.txt中配置即可
### 1.2 准备数据集
- 预处理文本提示数据集：下载下述链接内容后，将.jsonl文件移至INPUT目录下，将.json文件移至DETECTOR目录下

注：INPUT文件夹下已存在一个示例文件refcoco_testa.jsonl，DETECTOR文件夹下也存在一个示例文件refcoco_dets_dict.json

链接：https://pan.baidu.com/s/1UJmBULHizCFsORij8nbEAQ?pwd=lhzv 
提取码：lhzv 

- 图片数据获取：下载后存放在该目录下即可

http://images.cocodataset.org/zips/train2014.zip
### 1.3 运行示例
参数选择可参考main.py中的具体说明

```bash
python main.py --input_file ./INPUT/refcoco_testa.jsonl --image_root train2014  --gradcam_alpha 0.5 0.5 --box_method_aggregator sum --detector_file ./DETECTOR/refcoco_dets_dict.json --output_file ./OUTPUT/refcoco_testa.txt
```
### 1.4 结果说明
最终结果存储在OUTPUT目录下，其中的box坐标可供可视化结果进一步使用

注：该项目在OUTPUT目录下已给出部分运行结果



## 2 可视化结果展示
查看visualization.ipynb文件，参照OUTPUT中结果，修改image_path,box,bboxes等参数，直接运行该文件，可查看最终结果、候选单元、原图像等可视化结果

注：该代码可自行调整至main.py中使用


## 相关参考链接
- ReCLIP：https://github.com/allenai/reclip
- CLIP：https://github.com/openai/CLIP
