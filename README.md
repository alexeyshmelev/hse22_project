# Проект (майнор)

## Основная часть

### Статистика

|  | Длина генома | Количество скаффолдов | Количество аннотированных генов | Доля аннотированных генов | Количество участков с Z-DNA | Общаа длина участков Z-DNA |
| :-----------: | :-----------: | :-----------: | :-----------: | :-----------: | :-----------: | :-----------: |
| Plasmodium_vivax | 27013691 | 2748 | 5510 | 52.47 |
| Plasmodium_fragile | 25914542 | 248 | 5743 | 54.95 |
| Plasmodium_inui_San_Antonio_1 | 27405027 | 323 | 5879 | 47.47 |
| Plasmodium_coatneyi | 27685530 | 14 | 5575 | 50.81 |
| Plasmodium_cynomolgi_strain_B | 26181343 | 1663 | 5776 | 48.2 |

### Информация по полученным гомологичным кластерам

Всего кластеров: 5177

Кластеров, где встречаются белки для всех пяти организмов: 1

Во-первых, стоит сказать, что по неизвесным причинам ни при каки условиях (кроме как если практически совсем занулить порог при отборе Z-DNA, т.е. поставить его равным не 200, как сейчас, а 20, или увеличить интервал при выполнении bedtools slop, т.е. поставить его равным не 200, как сейчас, а 500) не находится более одного кластера, в котором бы встечались белки для всех 5 организмов, в которых есть Z-DNA. Поэтому, естественно, 5-10 кластеров я отобрать не смог и нарисовал картинку только для одного существующего, т.к. я посчитал, что настолько сильное снижение порогов, как указано выше, просто не имеет биологического смысла.

Думаю, это можт быть связано с тем, что у выбранных мною организмов был относительно низкий GC состав, хотя, как мне кажется, это должно было только повлиять на количство отобранных Z-DNA и их score, ведь в proteinortho мы подаём исходные .faa файлы, при анализе которых программа ничего не знает о наличи или отсутствии в этих белках Z-DNA (а в моём случае не находилось не только пересечения с генами, в которых есть Z-DNA, а вообще просто не было никаких общих белков, кроме как в одном случае).

![image](https://user-images.githubusercontent.com/60858323/174429590-fec095c1-b6c7-4348-af30-73ec7a570c34.png)

### Визуализация участков расположения Z-DNA

![clusters (1)](https://user-images.githubusercontent.com/60858323/174429993-6fbc711f-324c-41b1-814c-fbe8da132338.jpg)


## Бонусная часть
