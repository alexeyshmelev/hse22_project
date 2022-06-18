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

Думаю, это можт быть связано с тем, что у выбранных мною организмов был относительно низкий GC состав (~40%), хотя, как мне кажется, это должно было только повлиять на количство отобранных Z-DNA и их score, ведь в proteinortho мы подаём исходные .faa файлы, при анализе которых программа ничего не знает о наличи или отсутствии в этих белках Z-DNA (а в моём случае не находилось не только пересечения с генами, в которых есть Z-DNA, а вообще просто не было никаких общих белков, кроме как в одном случае).

Во-вторых, в нашей группе Apicomplexans было очень мало доступных геномов (всего 77, из которых достаточно много не имело ссылок на RefSeq), поэтому выбрать новые геном с **высоким** GC составом было практически невозможно (с учётом, что какие-то геномы уже были заняты другими участниками группы).

Также стоит отметить, что все организмы были одного рода - Plasmodium, что делает полученный результат во всего один общий кластер ещё более странным.

В-третьих, Plasmodium_fragile имел два гена в таблице анализа proteinortho, но один из них находился сильно дальше от текущего общего участка концентрации генов с Z-DNA, поэтому на картинке с визуализацией участков расположения Z-DNA я не стал его рисовать.

![image](https://user-images.githubusercontent.com/60858323/174429590-fec095c1-b6c7-4348-af30-73ec7a570c34.png)

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
