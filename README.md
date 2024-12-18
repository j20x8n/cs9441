java c
Department   of Electrical   Engineering 
EE   E4321.   Problem   Set   #9.   FinFET   layout,   Final   project   completion. 
Due:   December   11,   2024,   5   PM   EST   by   electronic   submission 
(This   part   is   to   be   completed   individually)
1.   In   this   problem, you   will   get   familar   with   some   of   the   capabilities, issues,   and challenges   with   modern   FinFET   technology   using   the   TSMC   N16   enablement.(a)   Using   schematic   simulation   wiith   the   standard      VT         devices      (pch svt mac and   nch svt mac),   estimate   the   fanout-of-four   (FO4)   delay   for   this   technology.   By   running   an   appropriate   simulation   with   the   nFET   device,   determine   the   subthreshold   slope   in   this   technology.   Use   a   supply   voltage   of   VDD      =   0.8   V.(b)   Create   a   DRC-   and   LVS-clean   layout   of an   inverter   with   four-finned   nFET   and   pFET   devices   of   minimum   length.    Please   include   taps   to   nwell   and   sub-   strate   in   your   layout.
(This   part   is   completed   with   your   project   partner.)
2.      For   the   Design   Project   final   submission,   please   submit   your   writeup   as   a single   PDF   file   attachment   submitted   by   only   one   person   of   your   two-person   team.   Please   note   clearly   in   the   document   the   name   of   the   two   team   members in   your   group.
To   submit   the   layout, please   stream   out   your   design   according   to   the   instructions on   the   class   website   and   attached   to   your   submission   as   well.
This   assignment   is   completion   of   your   final   project   and   should   be   done   with   your   project   partner.This   is   the   final   push   to   complete   the   entire   microprocessor   core   design.    You need   to   complete   three   more   (very   simple)   dataflow   blocks,   design   the   instruc-   tion   decoder,   and   assemble   the   final   design   (schematics   and   layout).   You   then   need to verify the functionality of   the entire design with Ultrasim from extracted   layout   (please   use   a   capacitance-only   extraction; wires   are   short   enough   that   this should be sufficient).   and determine your critical path timing with Spectre   from   extracted   layout.      In   addition,   you   will   want   to   verify   the   functionality   of your   design   at   clock   speed   with   a   (small)   number   of   patterns   in   Spectre.    Through   simulation,   calculate   the   average   power   dissipated   by   your   core   in   running   a “typical”   code   stream.      Try   to   determine   which   opcode   execution   (and   which   data   pattern   for   this   opcode) gives   the   worst   power   (in   general, this   can   be   quite difficult   to   do   for   a   complex   processor!).
There   are   three   remaining   dataflow   blocks   that   you   will   need   to   design   and   layout.
●   8-bit level-sensitive latch.   Use a gated-feedback, complementary代 写EE E4321. Problem Set #9. FinFET layout, Final project completion.Matlab
代做程序编程语言-pass-gate   design.    You   should   have   one   cell   layout   that   you   can   duplicate   8   times.   You   will   want   to    “separate”   the   accumulator   flip-flop   and   use   the   latch   positions   shown   in   the   datapath   diagram   of   Figure ??.       As      a      result,   three   of these   latches   will   be   used   in   the   datapath.
●   8-bit   3-to-1 multiplexer.   You   can   implement   this   with   a   3-nFET   basic   cell with   four   fully-decoded   select   lines   (orthogonal).
●   8-bit   bus   driver.         This   is   a   tristate   driver   with   an   enable   signal.       Once again,   a   single   cell   can   be   duplicated   8   times.

In   addition   to   these   dataflow   blocks,    you   need   to   design   the   instruction   decoder.       You      will      implement      this      as      a      static   psuedo-NMOS   PLA   with   the inputs   and   outputs   shown   in   Table   1.    instr      < 3 : 5 >   will   go   directly   to   the memory   as   the   address.   Take   advantage   of espresso   for   logic   minimization   and   make   use   of   don’t   cares   to   reduce   the   number   of   product   terms   required.
Be    sure    to    make    a    good    pencil-and-paper    floorplan    before    you    assemble   things   in Virtuoso. Remember to make good use of layout hierarchy. 
You   may   assume   that   the   instr   < 0 : 5 >   signal   is   arriving   before   the   rising edge   of   phi1   (but   after   the   rising   edge   of   phi2),   as   if   output   from   a   phi2   active-
Signal 
Direction 
Description 
instr < 0 : 2 > 
input 
opcode to decode 
subtract 
output 
subtract control for the adder 
mux cntl < 0 : 2 > 
output 
select lines for the 3-1 multiplexer 
drv   enable


output 
enable signal for the tristate bus driver 
mem write 
output 
write control for the memory 
mem   read


output 
read control for the memory 
shift bypass 
output 
shifter bypass 
load   bus


output 
load the internal bus externally 
store bus 
output 
load the internal bus to the external bus 
Table   1:   Inputs   and   outputs   of the   instruction   decoder   PLAhigh   latch.    bus   < 0 : 7 >   has   similar   timing   behavior.    This   means   that   the control   signals   going to the   shifter,   adder,   and   MUX   must   be   latched   by   a phi1   latch.   You   will   have   to   add   this   latch   to   the   design.
You   should   turn   in   the   following:
●   Waveforms   that   document   at-speed   operation   of   your   core.
●   Printouts   of the   key   schematics   of your   core   design.
●   A      short   write-up   that      documents   your      implementation      decisions,    your   power   estimates,   your   floorplanning   and   layout   planning,   and   your   func-
tional   verification.
●   Layout   submitted   electronically   for   evaluation.









         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
