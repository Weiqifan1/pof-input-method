# rime-pof-input-method
Pairs-of-five-strokes: An input method for writing Chinese characters on computers, 
primarily developed for the RIME input method editor.

# About the POF input method

Sound based input methods for chinese have been getting
better and better with predictive text enhancements,
but shape based input methods still have one big advantage
over the sound based ones: 
they help preventing character amnesia (提筆忘字).
The main problem with shape based input methods is that they are
hard to learn. This is because in order to be practical, 
any shape based system has to allow the user to write any character
with about the same number of keystrokes as sound based systems.
This means that in order to prevent ambiguity 
(the same keystrokes can write a large number of different characters)
the shape based systems use very complicated rules that make them hard to lean.

The motivation for creating the POF system was thus to create
a system that was easy to lean, could write any (common use)
character without the need for scrolling through a list,
yet using no more than 4 keystrokes pr. character plus the 1-9 numberkeys
for selection.

Here "common use" means that when using the POFsimp dict and schema files, 
you can write any of the first 5000 characters in this frequency list without
scrolling:

https://lingua.mtsu.edu/chinese-computing/statistics/char/list.php?Which=IM

When using the POFtrad dict and schema files, you can write 
any of the first 5000 characters in this frequency list without scrolling:

http://technology.chtsai.org/charfreq/sorted.html

This system contains a total of 28098 different characters taken from this repository:
https://github.com/stroke-input/stroke-input-data
compiled by Conway (@yawnoc).
Licensed under Creative Commons Attribution 4.0 International (CC-BY-4.0).

# How to use the POF system

To make it easy to learn, POF is fundamentally based on strokeorder.
It uses the standard 5 strokes in this order:

horizontal: 一 （heng 横， ti 提）

vertical： 丨 （shu 竖, shugou 竖钩）

left： 丿 （wan 弯, pie 撇）

right： 丶 （dian 点, na 捺）

bent： 乚 （all the bent strokes）

![img_01.png](images/img_01.png)

Each key correspond to two strokes according to this table:

![img_02.png](images/img_02.png)

For example, by pressing “g” you can write characters 
like 乙 （a single bent stroke）or 刁 （a bent stroke plus a horizontal stroke）
by pressing “m” you can write for example 七 or 匕

# Code examples

To write more complex characters, you combine keys like this:

戈 mw  (m 一乚 + w 丿丶 )

If the number of strokes is uneven, for the last stroke you 
use one of the keys where the second stroke is 一, that is you use either
T, Y, G, H or N:

戋 hdy （h 一一 + d 乚丿 + y 丶）

If the number of strokes is greater than 8, so you cant 
write the whole character with 4 keystrokes, you type the 
keys for the first 6 strokes, and the last two:

過 xnxs （x 亅乚 + n 亅一 + x 亅乚 + s 乚丶）

Some characters have a very complex set of strokes in the beginnning 
of the character that occur again and
again in many characters. This means that the 
last two strokes you would write with the last key are not enough 
to disambiguate.
The solution that POF uses is to use some keys to write certain
shapes that occur often. Those can be seen on 13 of the keys 
in the table above. Here are some examples:

䟿	sajw
橲	djjg
简	fcfh
蝝	jakw
睌	kdxq
挡	lcqh

餂	whbg
詔	edxh
駊	rdxy
緇	uafn
軪	iapt
鐑	oaog
䦘	pgmw

As you can see from the character 鐑 oaog
you only use a single key for these shapes if the shape is
at the start of the character.
So 鑫 is written owht and not ooo.

when writing the characters for the elemments themselves,
you can either use the the key:

食 w 言 e 馬 r 糸 u 車 i 金 o 足 s 木 d 竹 f 虫 j 目 k 手 l

but you can also write those 13 characters with just strokes

食 wphw 言 yhxh 馬 nhxo
糸 auw 車 jghn 金 whct 門 xhxh
足 xjky 木 jw 竹 tvj 
虫 xjl 目 xhh 手 tj

This means that if you are only going to write simplified
character, you will only have to learn the special 
functions for 6 keys on the middle row: sdf and jkl.

If you dont like to use this special functionaly, it is also possible
to write characters using up to 6 keystrokes instead of 4,
where you ignore the special functions of the 13 keys.

For excample 詔	edxh can instead be written 詔 hhxmrg or yhxmrg.

Chinese punctuation characters and parenthesis can be written 
using the ,. and z key. 

Examples:

, ，
. 。
z ，
z 。
zzz 《》
zzz 「」

# Guide to installing the POF input method

First install RIME (you can use the guide linked to below).

Then go to
C:\Users\USER\AppData\Roaming\Rime
and paste in the dict and schema files.

![img.png](images/img.png)

Open the file
default.custom.yaml
and add references to the two input methods

![img_1.png](images/img_1.png)

Then select rime from the list of input methods,

![img_2.png](images/img_2.png)

and then right-click on the 中 icon and clikc the 重新部署(R) key.

![img_3.png](images/img_3.png)

this should reload RIME, and you should then be able to select 
POF as your input method by pressing F4

![img_4.png](images/img_4.png)

You can then use it

![img_5.png](images/img_5.png)

If pressing the 重新部署(R) key doesnt reload the files, 
you might have to restart the computer to reload.


# Links to lean more about rime

* in Chinese:

https://rime.im/

https://github.com/rime/home

* in English:

https://geekbb.xlog.app/RIME?locale=en

https://www.laitimes.com/en/article/4roxi_588rc.html

https://hkdb.medium.com/cross-platform-chinese-input-engine-1dbd45d63dc5

https://hkdb.medium.com/rime-chinese-input-on-android-52fe73d0b7a6

# Online guide (in English) to install rime on Windows

https://wiki.michaelhan.net/Hanja_IME

# Other git repos for RIME input methods

* Wubi

(comes with RIME)

lookup: https://www.zdic.net

http://www.chinesemac.org/wubi/xing.html

https://indonesia-kita.com/WubiLearner_Intro.html

https://madmansnest.com/2018/03/26/wubi-introduction.html

https://www.reddit.com/r/ChineseLanguage/comments/2rjx05/free_webapp_for_learning_the_wubi_keyboard_layout

* Cangjie

https://github.com/rime/rime-cangjie

code lookup:

https://www.mdbg.net (click on the character and look at the right side).

or https://www.zdic.net/

https://dylansung.tripod.com/methods/cangjie_utf8.htm

https://en.wikipedia.org/wiki/Cangjie_input_method

* Zhengma

https://github.com/clayjar/rime-zhengma

https://github.com/Openvingen/rime-zhengma

character lookup: https://zhengma.911cha.com/

or https://www.zdic.net/

https://www.scribd.com/document/6082054/ZhengMa-Tutorial

https://en.wikibooks.org/wiki/Zhengma_Input

* Dayi

https://github.com/chiahsien/RimeDayi

https://en.wikibooks.org/wiki/Guide_to_Dayi_input/Introduction

* Array

https://github.com/rime/rime-array

https://en.wikibooks.org/wiki/Guide_to_Array_input

* G6

https://github.com/cyrus0880/rime-t9stroke

https://en.wikibooks.org/wiki/Guide_to_Array_input

//end

