# hse_hw2_chip
Bioinformatics HW2
Цель этого практического задания - определить участки генома, где присутствует определенная гистоновая модификация в конкретном типе клеток с помощью анализа ChIP-Seq данных. Для исследования я выбрала линию DND-41 и метку H3K9me3.  
## 1. fastqc 
Для того, чтобы правильно подгтотвить файлы и выяснить, нужно ли их обрабатывать дополнительно, посмотрим на отчет fastqc.  
##### ENCFF000AQB (реплика 1)  
Исходя из отчета fastqc, я бы сказала, что не нужно дополнительно обрабатывать чтения. Рассмотрим подробнее некоторые ключевые графики.  
![](https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_1.PNG)  
![](https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_2.PNG)  
![](https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_3.PNG)  
![](https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_4.PNG)    
  
Несмотря на то, что Per Tile Sequence Quality отмечен как непрошедший проверку качества график, мне кажется, что хотя и крастные "плитки" есть, их довольно мало, основное полотно синего цвета, который свидетельствует о хорошем качестве для tiles. (The graph allows you to look at the quality scores from each tile across all of your bases to see if there was a loss in quality associated with only one part of the flowcell).   
##### ENCFF000AQC (реплика 2)
Аналогичная ситуация со второй репликой.  
![](https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_1(1).PNG)  
![](https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_2(1).PNG)  
![](https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_3(1).PNG)  
![](https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_4(1).PNG)    
##### ENCFF000AOG (контроль)  
Для контроля отчет несколько лучше.  
![](https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_1(2).PNG)  
![](https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_2(2).PNG)  
![](https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_3(2).PNG)  
![](https://github.com/kseniashilova/hse_hw2_chip/blob/main/pic/fastqc_report_4(2).PNG)    

Я думаю, что действительно важный параметр, который можно было бы улучшить для второй реплики, это GC распределение, но мне кажется, что в целом сильно мы ничего не улучшим, и поэтому я приняла решение не использовать дополнительную обработку.  В целом, качество допустимое.  
