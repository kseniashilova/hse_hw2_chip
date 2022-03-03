# hse_hw2_chip
Bioinformatics HW2
Цель этого практического задания - определить участки генома, где присутствует определенная гистоновая модификация в конкретном типе клеток с помощью анализа ChIP-Seq данных. Для исследования я выбрала линию DND-41 и метку H3K9me3.  
  
Код находится в google colab notebook 
## 1. fastqc 
Для того, чтобы правильно подгтотвить файлы и выяснить, нужно ли их обрабатывать дополнительно, посмотрим на отчет fastqc.  
##### ENCFF000AQB (реплика 1)  
Исходя из отчета fastqc, я бы сказала, что не нужно дополнительно обрабатывать чтения. Рассмотрим подробнее некоторые ключевые графики.  
<img src="https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_1.PNG" alt="" width="500"/> <img src="https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_2.PNG" alt="" width="500"/>  <img src="https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_3.PNG" alt="" width="500"/> <img src="https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_4.PNG" alt="" width="500"/> 
 
  
Несмотря на то, что Per Tile Sequence Quality отмечен как непрошедший проверку качества график, мне кажется, что хотя и крастные "плитки" есть, их довольно мало, основное полотно синего цвета, который свидетельствует о хорошем качестве для tiles. (The graph allows you to look at the quality scores from each tile across all of your bases to see if there was a loss in quality associated with only one part of the flowcell).   
##### ENCFF000AQC (реплика 2)
Аналогичная ситуация со второй репликой.  
<img src="https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_1(1).PNG" alt="" width="500"/> <img src="https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_2(1).PNG" alt="" width="500"/>  <img src="https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_3(1).PNG" alt="" width="500"/> <img src="https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_4(1).PNG" alt="" width="500"/>   
##### ENCFF000AOG (контроль)  
Для контроля отчет несколько лучше.  
<img src="https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_1(2).PNG" alt="" width="500"/> <img src="https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_2(2).PNG" alt="" width="500"/>  <img src="https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_3(2).PNG" alt="" width="500"/> <img src="https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_4(2).PNG" alt="" width="500"/>    

##### Вывод
Основной график, показывающий качество ридов Per base sequence quality показывает отличные результаты качества ридов. Я думаю, что действительно важный параметр, который можно было бы улучшить для второй реплики, это GC распределение, но мне кажется, что в целом сильно мы ничего не улучшим, и поэтому я приняла решение не использовать дополнительную обработку. В целом, качество допустимое.    

## 2. Выравнивание на хромосому 5
|                        |      total reads |   aligned 0 times | aligned exactly 1 time| aligned >1 times |
|------------------------|------------------|-------------------|-----------------------|------------------|
|ENCFF000AQB (реплика 1) |   36077917       | 25577769 (70.90%) | 2266523 (6.28%)       |8233625 (22.82%)  |
|ENCFF000AQC (реплика 2) |   34325063       | 25931549 (75.55%) | 2091212 (6.09%)       |6302302 (18.36%)  |
|ENCFF000AOG (контроль)  |      41060673    | 31902898 (77.70%) | 2779973 (6.77%)       | 6377802 (15.53%) |
 
## 2. Venn diagram
##### ENCFF000AQB (реплика 1) 
<img src="https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/intervene_venn1_1.PNG" alt="" width="500"/>   <img src="https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/intervene_venn1_2.PNG" alt="" width="500"/>
##### ENCFF000AQC (реплика 2)
<img src="https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/intervene_venn2_1.PNG" alt="" width="500"/>   <img src="https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/intervene_venn2_2.PNG" alt="" width="500"/>

# Бонус
![](https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/result1.png)
![](https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/result2.png)
