В проекте была выбрана метка H3K36me3 и тип клеток HeLa-S3.
Те два файла, которые были выбраны имеют следующую гистограмму длин пиков.
![image](https://user-images.githubusercontent.com/48280238/121428343-5b508d00-c97e-11eb-9832-e4487fea39e6.png)
![image](https://user-images.githubusercontent.com/48280238/121428402-6d323000-c97e-11eb-9ee7-8e1a51d57362.png)
После фильтрации (2500 для первого файла и 500 для второго) были получены следующие гистограммы:
![image](https://user-images.githubusercontent.com/48280238/121429195-5213f000-c97f-11eb-9b72-3d6a71f2e3e4.png)
![image](https://user-images.githubusercontent.com/48280238/121429265-63f59300-c97f-11eb-9fde-99c38f14b7f6.png)

После это были построены pie-chart расположения гистоновых меток этих файлов: ENCFF054TNJ after filtering:
![image](https://user-images.githubusercontent.com/48280238/121429544-b33bc380-c97f-11eb-8a5f-2b1ff07401a1.png)
ENCFF348FNV after filtering:
![image](https://user-images.githubusercontent.com/48280238/121429770-f007ba80-c97f-11eb-99dd-c6520bc05e78.png)

Затем эти файлы были объединены в один отсортированный файл командой `cat *.filtered.bed | sort -k1, 1 -k2, 2n | bedtools merge > H3K36me3_HeLa.merge.bed`. Затем эти файлы были проверены в геномном браузере, что там действительно получилось объединение.

После этого был скачан файл со вторичной структурой командой `wget https://raw.githubusercontent.com/Nazar1997/DeepZ/master/annotation/DeepZ.bed`. После этого была посчитана гистограмма длин пиков для этого файла, а также аналогичный pie-chart:
![image](https://user-images.githubusercontent.com/48280238/121430649-06624600-c981-11eb-85d3-388ada8a5276.png)
![image](https://user-images.githubusercontent.com/48280238/121430819-40334c80-c981-11eb-91e1-cf764b3b21c7.png)

После этого были произведены пересечения метки и вторичной структурой. Получилась следующая гистограмма длин и pie-chart:
![image](https://user-images.githubusercontent.com/48280238/121431349-f5fe9b00-c981-11eb-9aa9-857979d82d0b.png)
![image](https://user-images.githubusercontent.com/48280238/121431600-4970e900-c982-11eb-82b6-adf68f1c56a8.png)

Затем этот файл был провизаулаизрован в геномном браузере ([сессия](http://genome.ucsc.edu/cgi-bin/hgTracks?db=hg19&lastVirtModeType=default&lastVirtModeExtraState=&virtModeType=default&virtMode=0&nonVirtPosition=&position=chr1%3A1565404%2D1566612&hgsid=1124216253_Xi0ARZzyCEigdozvgL4mL5P3ml7S))
![image](https://user-images.githubusercontent.com/48280238/121424013-8684ad80-c979-11eb-8334-83e3488c13d7.png)
chr1:1565813-1565845

После этого эти пересечения были проассоциированны с близжайшими генами. Получилось проассоциировать 834 генов (561 уникальных). Также был проведен GO анализ со следующими наиболее значимыми категориями:

nitrogen compound metabolic process

macromolecule metabolic process

organic substance metabolic process
