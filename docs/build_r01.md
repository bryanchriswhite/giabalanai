# giabalanai Build Guide ~ For rev.02 ~
* Click here for the build guide for rev.01 (https://github.com/3araht/giabalanai/blob/master/docs/build_r01.md) *

Please check whether it is rev.01 or rev.02 as it is written on the board.

The biggest difference between rev.01 and rev.02 is how to implement the front and back of Pro Micro. Since rev.02 is a 4 mm shakotan, the front side of the Pro Micro is facing the board side to be mounted.

** It is recommended to read everything once before assembling. ** **


## 0 Checking parts and organizing the mounting surface of each part
### Kit accessories

| Part name | Quantity | Remarks |
| -------- | ------- | ------- |
| Left-hand side board | 1 sheet | Keys are arranged in a parallelogram in 5 rows and 12 columns. |
| Right-hand side board | 1 sheet | Keys are arranged in 12 rows, 13 rows, 12 rows, 13 rows, and 12 rows from the top, and an encoder is arranged at the right end. |
| Bottom plate | 2 sheets | Use the same bottom plate for both the left-hand side board and the right-hand side board. |
| M2 spacers | 20 pieces | 10 pieces each on the left and right |
| M2 screws | 40 pcs | 20 pcs each on the left and right |
Cushion seal | 10 pieces | 5 pieces each on the left and right |
| TRRS jack | 2 | For TRRS cable connecting left and right boards |
| Reset switch | 2 | Used when writing firmware. |
Diode 1N4148 | 99 pieces | 60 pieces on the left hand side, 38 pieces on the right hand side + 1 piece for encoder |

There are 62 buttons on the right-hand side, but 24 of them have overlapping sounds, so 24 diodes are required and 38 on the right-hand side are sufficient.
Add the encoder to it and use 39 diodes on the right side.


### Items that need to be prepared separately

| Part name | Quantity | Remarks |
| -------- | ------- | -------- |
| [Pro Micro (with conthrough)] (https://yushakobo.jp/shop/promicro-spring-pinheader/) | 2 | Please select without firmware (write separately). |
| Key switch (Cherry MX compatible product) | 122 pieces | Left hand side 60 pieces + Right hand side 62 pieces. |
| MX compatible keycaps | 122 pieces | 1U, left 60 pieces + right 62 pieces. (5pin type recommended) |
| [TRRS cable] (https://yushakobo.jp/shop/trrs_cable/) | 1 | 4 pole cable for 3.5mm audio, also known as AUX cable Cable required). |
| [Micro USB cable] (https://yushakobo.jp/shop/usb_cable_micro_b/) | 1 | Pro Micro side connector has low durability, so magnet type is recommended. This is very convenient when writing firmware to the Pro Micro on the left and right boards. Also, since the cable must be capable of data communication, the charging cable cannot be used. If you can't write the Hex file, check the cable. |

### [Optional] Items that need to be prepared separately

| Part name | Quantity | Remarks |
| -------- | ------- | ------- |
| [Rotary encoder (with knob)] (https://yushakobo.jp/shop/pec12r-4222f-s0024/) | 1 piece | Placed on the keyboard on the right hand side. Required when installing a rotary encoder for volume adjustment + mute. You can switch layers by pressing and holding + 〇〇, so I think it is better to have it. |
| LED (SK6812mini) | 123 | Required when using 2 "Backlight RGB LEDs". 60 on the left + 62 on the right + 1 for encoder. Since it involves difficult soldering, we recommend that beginners of soldering assemble without LEDs. |

### Front and back mountings

** * There is an order for mounting parts. In particular, the Pro Micro, key switch, and encoder will be installed last, so be careful not to implement them first.
Follow the steps below for the mounting order. ** **

The diode mounting location and keyboard name are printed on the back of the board.

Left hand side front side
<img width = "700" alt = "PCB" src = "https://github.com/3araht/giabalanai/blob/master/pictures/left_front_pcb_r02.jpg">

Left hand side back side
<img width = "700" alt = "PCB" src = "https://github.com/3araht/giabalanai/blob/master/pictures/left_rear_pcb_r02.jpg">

Right hand side front side
<img width = "700" alt = "PCB" src = "https://github.com/3araht/giabalanai/blob/master/pictures/right_front_pcb_r02.jpg">

Right hand side back side
<img width = "700" alt = "PCB" src = "https://github.com/3araht/giabalanai/blob/master/pictures/right_rear_pcb_r02.jpg">


#### Mount the following parts on the back side
 --LED [Optional]
 - diode
 --TRRS jack
 --Reset switch
 --Pro Micro

#### Mount the following parts on the front side
 --Key switch
 --Encoder


## 1 Diode installation
On keyboards with a large number of keys, a technique called Matrix is ​​used to determine if a key has been pressed.
This diode is unnecessary if it is guaranteed that only one key will be pressed at a time.
Since I sometimes play chords, there are occasions when I press multiple keys at the same time.
At this time, this diode is required to correctly judge multiple simultaneous pushes by the method called Matrix.
For a detailed explanation, see [here] (https://docs.qmk.fm/#/how_a_matrix_works).

The diode has a direction. Also, bend your legs as shown.
If you pinch the diode and bend the legs at both ends at the same time, the shape will be relatively good as shown on the right of the figure.
<img width = "700" alt = "diode" src = "https://github.com/3araht/giabalanai/blob/master/pictures/diode_bend.jpg">

The diode is mounted on the back of the board so that it does not interfere with the keyswitch.
Arrange the black line of the diode so that it fits the square footprint (the one printed with K, K seems to be an acronym for Kathode (Germany), but with K in black (Kuro)).
<img width = "700" alt = "diode" src = "https://github.com/3araht/giabalanai/blob/master/pictures/diode_align1.jpg">

Bend your legs and crawl on the board to temporarily fix the diode.
<img width = "700" alt = "diode" src = "https://github.com/3araht/giabalanai/blob/master/pictures/diode_flatten.jpg">

View from the front side
<img width = "700" alt = "diode" src = "https://github.com/3araht/giabalanai/blob/master/pictures/diode_flatten2.jpg">

Solder from the front side.
<img width = "700" alt = "diode" src = "https://github.com/3araht/giabalanai/blob/master/pictures/diode_soldered.jpg">

Cut your legs with nippers. Your legs will fly vigorously, so it's a good idea to hold your legs while cutting.
<img width = "700" alt = "diode" src = "https://github.com/3araht/giabalanai/blob/master/pictures/diode_feet_cut.jpg">

Solder this to 60 places on the left-hand side board and 39 places on the right-hand side board.

Nothing is implemented in R1 in the figure below.
<img width = "700" alt = "diode" src = "https://github.com/3araht/giabalanai/blob/master/pictures/R1_NoSolder.jpg">


## 2 Backlight RGB LED installation [Optional]
Image training is important, so first check out the video that introduces the soldering process in "SK6812mini Soldering".
Also, using the following is the key to success.
--Set the temperature to 200 ° C to 220 ° C with a soldering iron with temperature control function.
--Use lead-containing solder (eutectic solder) with a low melting point

The chip LED (SK6812mini) for the backlight is mounted from the back side of the PCB. Pay attention to the orientation and insert it into the hole.
When viewed from the back of the LED, the largest pad (5V) and silk (printing) ○ are in the same position.
For the convenience of transmitting data in series, the LEDs are lined up from left to right when viewed from the front side, the second line from right to left, the third line from left to right, and so on (in the case of the right hand side). ).
<img width = "700" alt = "RGB_LED" src = "https://github.com/3araht/giabalanai/blob/master/pictures/LED_serial.jpg">

Therefore, please note that the directions of the LEDs on the even and odd rows are different.
It's easy to get the wrong direction when the soldering is on track.
Speaking of shock at that time. .. .. (Experienced person talk).
<img width = "700" alt = "RGB_LED" src = "https://github.com/3araht/giabalanai/blob/master/pictures/SK6812mini_alignment.jpg">

Use a temperature-controlled soldering iron to solder at approximately 220 ° C. Please note that the LED will break if the temperature is high.
A soldering iron that cannot control the temperature will burn and break immediately (this is also an experienced person).

I found that it is easier to do it by tilting the trowel and expanding the contact area.
<img width = "700" alt = "RGB_LED" src = "https://github.com/3araht/giabalanai/blob/master/pictures/LED_solder_iron.jpg">

**important point**  
When mounting the LED right next to the Pro Micro on the right hand side, be careful not to get it on the B6 pin.
<img
