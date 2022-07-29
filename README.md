# main
program
make a first example
n o i n f y e t = 1 ! no I n f has been found y et
2 scaledsmax = 0
3 ! i n d i c a t e s whether A ( i ) f i n i t e but
4 ! abs ( r e a l (A ( i ) ) ) + abs ( imag (A ( i ) ) ) = I n f
5 smax = −1
6 do i = 1: n
7 i f ( i snan ( r e al (A ( i ) ) ) . or . i snan ( imag (A ( i ) ) ) ) then
8 ! r e t u r n when f i r s t NaN found
9 icamax = i , re tu rn
10 e l s e i f ( n o i n f y e t == 1 ) ! no I n f found y et
11 i f ( i s i n f ( r e al (A ( i ) ) ) . or . i s i n f ( imag (A ( i ) ) ) ) then
12 ! re co rd l o c a t i o n of f i r s t I nf ,
13 ! keep l o o k i n g f o r f i r s t NaN
14 icamax = i , n o i n f y e t = 0
15 else ! s t i l l no I n f found y et
16 i f ( scaledsmax == 0 )
17 ! no abs ( r e a l (A ( i ) ) ) + abs ( imag (A ( i ) ) ) = I n f y et
18 x = abs ( r e al (A ( i ) ) ) + abs ( imag (A ( i ) ) )
19 i f ( i s i n f ( x ) )
20 scaledsmax = 1
21 smax = ( . 2 5 *
abs ( r e al (A ( i ) ) ) ) + ( . 2 5 *
abs ( imag (A ( i ) ) ) )
22 icamax = i
23 e l s e i f ( x > smax ) ! e v e r yt h i n g f i n i t e so f a r
24 smax = x
25 icamax = i
26 endi f
27 else ! scaledsmax = 1
28 x = ( . 2 5 *
abs ( r e al (A ( i ) ) ) ) + ( . 2 5 *
abs ( imag (A ( i ) ) ) )
29 i f ( x > smax )
30 smax = x
31 icamax = i
32 endi f
33 endi f
34 endi f
35 endi f
36 enddo
