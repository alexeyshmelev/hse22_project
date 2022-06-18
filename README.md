# Проект (майнор)

## Основная часть

### Статистика

|  | Длина генома | Количество скаффолдов | Количество аннотированных генов | Доля аннотированных генов | Количество участков с Z-DNA | Общаа длина участков Z-DNA |
| :-----------: | :-----------: | :-----------: | :-----------: | :-----------: | :-----------: | :-----------: |
| Plasmodium_vivax | 27013691 | 2748 | 5510 | 52.47 | 11274 | 112614 |
| Plasmodium_fragile | 25914542 | 248 | 5743 | 54.95 | 7586 | 77100 |
| Plasmodium_inui_San_Antonio_1 | 27405027 | 323 | 5879 | 47.47 | 16259 | 163070 |
| Plasmodium_coatneyi | 27685530 | 14 | 5575 | 50.81 | 8090 | 81596 |
| Plasmodium_cynomolgi_strain_B | 26181343 | 1663 | 5776 | 48.2 | 8767 | 87412 |

### Гистограммы значений ZH-score

![Plasmodium_inui_San_Antonio_1_hist](https://user-images.githubusercontent.com/60858323/174435846-58ca728d-c96c-4242-b1fe-16601e4b648a.jpg)
![Plasmodium_cynomolgi_strain_B_hist](https://user-images.githubusercontent.com/60858323/174435847-d1eb31c4-5e96-4fea-9c4c-6186cf59354c.jpg)
![Plasmodium_coatneyi_hist](https://user-images.githubusercontent.com/60858323/174435849-c3ef2d1f-3a9a-4b0a-9009-9305ee333cc1.jpg)
![Plasmodium_fragile_hist](https://user-images.githubusercontent.com/60858323/174435852-b29ddc23-5740-469d-960d-43b4a23ec174.jpg)
![Plasmodium_vivax_hist](https://user-images.githubusercontent.com/60858323/174435856-ce95b0fd-56cf-4991-baf5-e187aa6653a8.jpg)


### Информация по полученным гомологичным кластерам

Всего кластеров: 5177

Кластеров, где встречаются белки для всех пяти организмов: 1

Во-первых, стоит сказать, что по неизвесным причинам ни при каки условиях (кроме как если практически совсем занулить порог при отборе Z-DNA, т.е. поставить его равным не 200, как сейчас, а 20, или увеличить интервал при выполнении bedtools slop, т.е. поставить его равным не 200, как сейчас, а 500) не находится более одного кластера, в котором бы встечались белки для всех 5 организмов, в которых есть Z-DNA. Поэтому, естественно, 5-10 кластеров я отобрать не смог и нарисовал картинку только для одного существующего, т.к. я посчитал, что настолько сильное снижение порогов, как указано выше, просто не имеет биологического смысла.

Думаю, это можт быть связано с тем, что у выбранных мною организмов был относительно низкий GC состав (~40%), хотя, как мне кажется, это должно было только повлиять на количство отобранных Z-DNA и их score, ведь в proteinortho мы подаём исходные .faa файлы, при анализе которых программа ничего не знает о наличи или отсутствии в этих белках Z-DNA (а в моём случае не находилось не только пересечения с генами, в которых есть Z-DNA, а вообще просто не было никаких общих белков, кроме как в одном случае).

Во-вторых, в нашей группе Apicomplexans было очень мало доступных геномов (всего 77, из которых достаточно много не имело ссылок на RefSeq), поэтому выбрать новые геном с **высоким** GC составом было практически невозможно (с учётом, что какие-то геномы уже были заняты другими участниками группы).

Также стоит отметить, что все организмы были одного рода - Plasmodium, что делает полученный результат во всего один общий кластер ещё более странным.

В-третьих, Plasmodium_fragile имел два гена в таблице анализа proteinortho, но один из них находился сильно дальше от текущего общего участка концентрации генов с Z-DNA, поэтому на картинке с визуализацией участков расположения Z-DNA я не стал его рисовать.

![image](https://user-images.githubusercontent.com/60858323/174429590-fec095c1-b6c7-4348-af30-73ec7a570c34.png)

### Таблица с информацией по существующему кластеру

| Количество генов | Гены | Функции генов | Расположение Z-DNA | Z-score |
| :-----------: | :-----------: | :-----------: | :-----------: | :-----------: |
| 1 | XP_001613463.1 |  | В промотере | 273.5761 |
| 1 | XP_004220722.1 |  | В промотере | 234.5918 |
| 1 | XP_008816785.1 |  | В промотере | 712.187 |
| 1 | XP_012334081.1 |  | В промотере | 612.3848 |
| 2 | XP_019912731.1, XP_019912540.1 |  | В промотере | 883.5764 (для последнего) |

### Выравнивание

<details><summary>Выравнивание для единственного кластера</summary>

  ```
  >XP_008816785.1
M-------------------------------------------------------------------------------
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
------EATNRPGGRGPQNRPGNRPV-SRGGYMA-ANRGGNNAA----YRGANQSANRAANGVGRVTHSETARVTQSETT
KV----TAKESEKKPMDNAANQGRNNTANGIEKRAST-------------------------------------------
--------------------------------------------------------------------------------
-------------EPEKKIPH----------------ETEKATSQLANQAINGGVKETPNKLADKVA-RGPPNRDASKAA
DGYNKYS-----------------NNSNNSNSSNSSNCNNSGSQDGILKTGSFVSRDGLELKTYEWVVDKPVGIIILVHA
LNSHVRFEYLKLNAIIESKEKATLVDANNYYIYKDSWIEQFNKSGYSVYGLDMRGHGQSGCVKNVKTHVNAFQDLVYDVL
EYANIVYDSLSTEGKKKKKENITSHGGGVKTSSDTASSV-----ASTSDYDGNIPQGSHVSPGKNPYSGKQQP-------
-----------------PPSGVNNIS-KNDVPPFYFMGLSMGGNIVLRILQLREKKGD-ESIKRLNIKGVITLAGMISLD
DLKKKPEYKYFYVPMAKLASALLPTKRLAPLLKLEMFPYINDLFRFDPHCYNKPITNRLGNELLKAVDSLHNDIRFIPED
VQILIIHSVRDSACSYTGVSKFFNTIQTKNKELFTLHDMDHILPQEPGNERILKKVIDWLAHLQCAKG
>XP_004220722.1
MA------------------------------------------------------------------------------
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
------EVTNKPAGRGPQNRPGNRPT-NRGGNKA-ANRGPNQSA----NQPANKTPNRAPNGVPRVTQNETARVTQSEAA
RVTQSETAKESEKKAMNNAANQAENKTSNEIEKKTSAEPEKKAAAEPEK-------------------------------
---------------------------------------------------------KAAAEPEKKASAEPEKKAAAEPE
KKTQTEPEKKTPIEPEKKIPD----------------ETEKATSGSANKETRQTEKETPHKVADKVA-KESPNRDANKAA
NRDANKAANRDADKAANRDANKAANRDANKAANKAADGDNDGRQNDILKTGSFISRDGLELKTYEWVVNKPVGIIILVHA
LNSHVRFEYLKHNVIIESKEKAILVDAKNYYIYKGSWIEQFNKRGYSVYGLDMRGHGQSGCVQNVKTHVNDFQELVYDVL
EYANIVYDSLCSGSASS--------------------------------------------------SKEQ---------
-----------------LPSGMNNIK-KNDIPPFYFMGLSMGGNIVLRVLELREKKGD-ESIKRLNIKGVISLAGMISLD
DLKKKPEYKYFYLPIAKLASTLLPTMRLSPVLKFEMFPYINDLFSFDANCYHKPITNRFGNEILKAVDALHNDIRFIPED
VQILIVHSVLDSACSYTGVSKFFNSIQTKNKELFTIDDMDHILPQEPGNEKILKKVIDWLAQLQ----
>XP_001613463.1
MT------------------------------------------------------------------------------
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
------EATNRPAGRGPQNRPGNRPA-NRGGNKA-ANRGANQSA----SQPANKAPNRVTNGVARATQGETTKVTQSDTA
KV----TAKESEKEAMNNTANQAGNKTATEPERKASPEPEKKAPSEPEKKVPIEPDRKVSSEPERKISSEPERKAVTEPE
RKISSEPERKASTEAERKASTEAERKISSEPERKASTEAEKRTSPEPEKKTSNEPERKVSTEPEKKVSIEPEKKVSIEPD
KKAPTEPERKAPTEPERKVPAEPEKKAPTDAERKVSTEPEKATGQPAKQAISGGAKEAINQ-TEKGA-KETPNRDANKAA
IAASAPATSAPA------------TSAAATSAAAAAAPDDGGSQSGALKTGSFVSRDGLELKTYEWVVNKPVGIILLVHA
LNSHVRFEYLKHNVIIESKEKATLLDGKNYYIYKDSWIEQLNKNGYSVYGLDMRGHGQSGCVQNVKTHINDFHDLVYDVL
EYANIVYDSLCTGGKKKKKK---SPSGGVNTSSDTAPSGGLSSSASSSDDD-DTSQGSRTSSGNAPPSGANSVRRSDANS
MKRSDANNMRRSDANNMRRSDANNMR-RSDVPPFFLMGLSMGGNIVLRILELGGKKGD-ESIKRLNIKGVISLAGMISLD
DLKKKPEYKYFYIPMGKLASMVLPTMRMTPSLNFKMFPFINDLFSFDAHCYPKPVTNRFGSELLKAVDALRNDVKFIPEE
AQILLVHSVLDSACSYNGVLKFFKSIQTKNKELFTIEDMDHILPLEPGNERILKKVIDWLAQLQCVRG
>XP_012334081.1
M-------------------------------------------------------------------------------
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
--------------------------------------------------------------------------------
------DASNKGASRVPQNRAGNKPVATRGGNRAVPQRGVKQPVA---QTPASNVPSRAPTGVTRVTQNETTRVN-----
-------VKESEK--------------------KIST-------------------------------------------
--------------------------------------------------------------------------------
-------------GPERKIMD----------------EREKARGPIAQKEPLRQAG-GTNRLGDKGIKEESPNRDTKKVG
--------------------------------------GNNGIENDMCKKGTFLSRDGLELKTYAWVVKNPVGIIILVHA
LNSHVRFEYLKHNVIIESKEKVTLVDKNNYYIYKDSWIERLNKSGYSVYSLDLRGHGQSACVQNVKTYVNRFKDLVYDVM
DYANSVYDSLCEEQKTKTNN--AACGDGVNNATDMGSSG-----ALTSDNE-NTRPGSQPSTDNAPSTQNN---------
-----------------NSSDVNASTKTNQIPPFYFMGLSMGGNIVLRILELREKKKKVQLIKRLNIKGVISLAGMISLD
DLKKKPEYKYFYIPVAKLAATLMPTRRLSPALKFEMFPYINDLYEFDPHCYCKSITNRLGNELLKAVDALHNDMKYMPED
VQMLFVHSTKDSACSYTGVSKFFNALKTTKKELFTIEDMDHILPLEPGNDKILKKVIDWLSKMHYV--
>XP_019912540.1
MAEAQSMELDNKPGRGGGGSCSTGLRGSAGSARLDGKPKVDSFHNRDGLKLKTYSWLVKNPIGVIFLVHGLNTNLRLEYM
RHNVDIVSPEKAILKDADNYYVYKDSWIEHLNKNGYSVYGMDHQGHGLSDGWRNLKTHVKKFDDMVYDLIQYINRVHDLM
CLRGQKDELSGETSKSSSSASPKSITSPSSPTSAPSPTSLAQRNNVSSSIHNNLKNTKMPPFYIMGLSMGGNIVLRTLEI
LEKSKDHNAKLNIKGCICLAGMISIDELATKASYKYFYIPFGKFLAAVFPTLRLTPSLYFKKYPYVNQIFKYDKNRYKKP
ITCKLGYELLNAIENLHNDIDHIPKDTPILFVHSKHDSACFFGGAETFFKKINTNLKELHVLDDMDHVLTMEPGNERVLQ
KRQTTMSNTNKGAGRGFQNRPGNRPA-NRGDNRA-PNRGTNQSTNQSTNQPANKAPNRAPNGVTRVTQSETTKVS-----
-------AKEIEK--------------------MTST-------------------------------------------
--------------------------------------------------------------------------------
-------------EPNKKIPV----------------QTGKATSQLA--------KGTPNKLADKVA-KDPPNMHTNKTT
------------------------------------DNNNKVEQNDILKTGSFKSRDGLELKTYEWVVDNPVGIIMLVHA
LNCHVRFEYLKHNAIIESKEKATLIDKNNYYLYKGSWIEQFNKNGYSVYGLDMRGHGESGCVKNVKTHINNFQDLIRDVV
QYANIVYDSLCEPGKKNNKK--KAANGGVNTSNDGE----------SSDNE-ETSQGTHPSPGNTPSSRGQ---------
-----------------TPSTVNSSS-KNDVPPFYFMGLSMGGNIVLRILQLREKKGD-ESIKRLNIKGVISLAGMISLD
DLKKKPEYKYFYIPIAKIAAALLPTMRLGPYLKFEMFPYINDLFSFDPHCYPKAITNRFGNELLKAVDALHKDMKYIPED
VQILFVHSVLDSACSYTGVSKFFNALKTKNKELFTIEDMDHILPLEPGNERILKKVIDWLAQLQSVKA
  ```
  
</details>

### Визуализация участков расположения Z-DNA

![clusters (1)](https://user-images.githubusercontent.com/60858323/174429993-6fbc711f-324c-41b1-814c-fbe8da132338.jpg)


## Бонусная часть

При поиске квадруплексов с помощбю следующего регулярного выражения:

```
(?:C{5,}[ATGC]{1,12}){5,}C{5,}
```
во всех пяти организмах находится 0 квадруплексов. А при использовании более мягкого условия:

```
(?:C{3,}[ATGC]{1,12}){3,}C{3,}
```
только в одном организме находится 51 квадруплекс (Plasmodium_inui_San_Antonio_1). Следовательно, общие кластеры для всех пяти организмов с квадруплексами в генах выделить нельзя (также это ещё раз проверено в коде с помощью intersectBed, что пересечения нет), поэтому просто нарисуем расположение первых пяти из найденных квадруплексов относительно генов. Получим:

![quadruplex](https://user-images.githubusercontent.com/60858323/174441367-f58d4e4c-ad98-44b5-944b-30c07814df9e.jpg)
