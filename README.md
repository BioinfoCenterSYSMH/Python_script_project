# Python_script_project
> 001oneButtonToGseaFile.py 一键处理表达谱生成可以用来做GSEA分析的脚本

* 要注意的是 input file 和 annotation file 的第一行都需要用 <span style="color:blue">#</span> 注释, 详见实例文件.

* 由于编者的习惯, 将表达谱第一列的格式规定为 gene_name(ensg_id)(gene_type), 这个在gtf文件中可以提取到的.

```
usage:

python 001oneButtonToGseaFile.py --input [] --annotation [] --outputPrefix []

optional arguments:
  -h, --help            show this help message and exit
  --input INPUT, -I INPUT
                        整理好的输入文件,第一行以#注释
  --annotation ANNOTATION, -A ANNOTATION
                        分组注释文件
  --outputPrefix OUTPUTPREFIX, -O OUTPUTPREFIX
                        输出文件的前缀,可以附带目录
```


> 002gzConvertToGgplotFormat.py  ***computeMatrix工具得到的输出的压缩.gz矩阵文件结果整理成长表格形式***
* usage
```
python 002gzConvertToGgplotFormat.py --input sample.gz --outputPrefix ... [option]

optional arguments:
  -h, --help            show this help message and exit
  --input INPUT, -I INPUT
                        Input of gz format file
  --outputPrefix OUTPUTPREFIX, -O OUTPUTPREFIX
                        PrefixName of the result file
  --averageType AVERAGETYPE, -t AVERAGETYPE
                        The type of statistic that should be used for the profile. The options are:"mean","median","min","max","sum","std";
                        Specify more than one averageType, separate with commas
  --sample SAMPLE, -s SAMPLE
                        Enter the sample list to be extracted, separated by commas: sample1,sample2,...,sampleN
```
* output
  * 输出文件为可以直接用来作图的整合矩阵,第一列为bin编号,第二列...指定列为峰信号均值[...其他统计值],倒数第二列为样本名,倒数第一列为peak名.

| bin  | mean                 | ...  | sampleName | peakName      |
| ---- | -------------------- | ---- | ---------- | ------------- |
| 1    | 0.037430114503816794 | ...  | H3K27ac    | promoter.trio |
| 2    | 0.03541725190839695  | ...  | H3K27ac    | promoter.trio |
| 3    | 0.03517291348600509  | ...  | H3K27ac    | promoter.trio |
| 4    | 0.03546380152671756  | ...  | H3K27ac    | promoter.trio |
| 5    | 0.034288638676844785 | ...  | H3K27ac    | promoter.trio |
| 6    | 0.03518454961832061  | ...  | H3K27ac    | promoter.trio |
| 7    | 0.036569127226463105 | ...  | H3K27ac    | promoter.trio |
| 8    | 0.03578956488549618  | ...  | H3K27ac    | promoter.trio |
| 9    | 0.033881422391857506 | ...  | H3K27ac    | promoter.trio |
| 10   | 0.03516126717557252  | ...  | H3K27ac    | promoter.trio |

* before

 ![输入图片说明](https://images.gitee.com/uploads/images/2020/1023/111958_d385336c_7948144.png "屏幕截图.png")
 
* after
 
 ![输入图片说明](https://images.gitee.com/uploads/images/2020/1023/112015_3651ddd4_7948144.png "屏幕截图.png")
