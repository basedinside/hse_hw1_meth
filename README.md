# Ссылка на колаб

https://colab.research.google.com/drive/1aUuEbLNQlG8hDfm5UQuRooUq6_gyfHVK?usp=sharing

# Основная часть

## Задание 1

Для отчета я взял файл SRR3824222_1. После построения FASTQC отчета обнаружилось несколько аномалий.

Низкое содержание С и неравномерное распределение оснований. В теории значения должны колебаться в районе 25%, чего здесь не наблюдается. 

Возможно, такой результат связан с особенностями секвенирования.

![image](https://user-images.githubusercontent.com/71254839/154859469-37966691-a4ed-481c-9a4f-c5727c4dce46.png)

[В соответствии с документацией](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/Help/3%20Analysis%20Modules/5%20Per%20Sequence%20GC%20Content.html), это означает, что девиации от высчитанного распределения наблюдается более, чем в 15% ридов

![image](https://user-images.githubusercontent.com/71254839/154859557-f64fa978-73ac-421e-9523-2f9d4c56ccb1.png)

Здесь все нормально, потому что предупреждение возникает при условии, что не все риды одной длины, при этом считается нормой наличие одного пика. Отсутствие ошибки свидетельствует о том, что все риды имеют ненулевую длину 

![image](https://user-images.githubusercontent.com/71254839/154859828-dd2c6913-388a-4c0f-9f1c-5bdccb18cc0f.png)

## Задание 2

### a)

|          | 11347700-11367700 | 40185800-40195800 |
| -------- | ----------------- | ----------------- |
| 8 Cell   | 1090              | 464               |
| icm      | 1456              | 630               |
| Epiblast | 2328              | 1062              | 

### b)

```bash
!find -name "*bt2_pe.bam" | xargs -P 3 deduplicate_bismark  --bam  --paired
```

### d)



### e)

Если выстроить гистограммы в ряд, то получим сходство со статейными данными. Наблюдаем спад, затем подъем, затем снова спад и затем подъем.

|Полученный результат|Научные результаты|
|--------------------|------------------|
|![Картинка](https://github.com/basedinside/hse_hw1_meth/blob/main/Data/Screenshots/histplot.png)|![image](https://user-images.githubusercontent.com/71254839/154860541-0b8128b4-b541-460c-9448-7ca93abff6fc.png)|

### f)

Визуализация совместных треков. Файл конфигурации есть в [репозитории](https://github.com/basedinside/hse_hw1_meth/blob/main/src/tracks.ini.txt).

![Картинка](https://github.com/basedinside/hse_hw1_meth/blob/main/Data/Screenshots/combined.png)
