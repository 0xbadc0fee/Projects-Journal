
# Table of Contents

1.  [Summary](#org24f688e)
2.  [Links / Resources](#org729c5e9)
    1.  [Master Model (C)](#org39d862d)
    2.  [IEC FBD Model](#org779c4e1)
    3.  [IEC ST Model](#org8cd5903)
3.  [Program Model](#orgfcc2fb5)
    1.  [Model: Abstract](#orgf5b1f3b)
        1.  [Top-Down Program Flow & Checklist <code>[0%]</code>](#org92d35c5)
    2.  [Model: C](#org33a040a)
    3.  [Model: IEC FBD](#orgb1a6692)
        1.  [Program Flow & Checklist <code>[%]</code>](#org376e781)
    4.  [Model: IEC ST](#orge5a48a7)
        1.  [Program Flow & Checklist <code>[%]</code>](#orgf9784e6)
4.  [Program Code](#orgdb78553)



<a id="org24f688e"></a>

# Summary

Based off of the ESX-4CT\_Example that ships with target support package “ESX.4ctC TSP 23-0A”.  It has full logic + hardware + comms + opensyde server functionality (#L3).  Can use this as a model to remake in IEC FBD and IEC ST.  [OPTIONAL] Once running same as C type example, can work backwards, stripping out functions to create #L2 and #L1 type examples if we want.


<a id="org729c5e9"></a>

# Links / Resources


<a id="org39d862d"></a>

## Master Model (C)

-   ESX-4CT\_Example.rtf
-   ESX-4CT\_Example.syde


<a id="org779c4e1"></a>

## IEC FBD Model

-   TBD


<a id="org8cd5903"></a>

## IEC ST Model

-   TBD


<a id="orgfcc2fb5"></a>

# Program Model


<a id="orgf5b1f3b"></a>

## Model: Abstract


<a id="org92d35c5"></a>

### Top-Down Program Flow & Checklist <code>[0%]</code>

-   See "@" note for lines in original example
-   [ ] PREPROC <code>[0/0]</code>
-   [ ] INIT TASK(s) <code>[0/2]</code>
    -   [ ] COMMS <code>[0/9]</code>
        -   [ ] Initialize CAN
        -   [ ] Initialize Tx on CAN1
        -   [ ] Build Startup Tx MSG
        -   [ ] Initialize Rx on CAN1
        -   [ ] Start openSYDE Server
        -   [ ] Send Startup Tx MSG
        -   [ ] ?? 134 ??
        -   [ ] ?? Deadlock / ICC Safety Guard ??
        -   [ ] ?? LED physical debug INIT setup ??
    -   [ ] I/O <code>[0/7]</code>
        -   [ ] Initialize Uext (external voltage outpu)
        -   [ ] Allow usage of outputs via MainSwitch flag
        -   [ ] Initialize IO pwm\_output
        -   [ ] Initialize IO digital\_out
        -   [ ] Initialize IO voltage\_in
        -   [ ] Initialize IO digital\_in
        -   [ ] Initialize IO voltage\_in
-   [ ] CYCLIC TASK(s) <code>[0/2]</code>
    -   [ ] DO 
        -   [ ] SET pwm out
            -   FROM: DataPool / HMI
            -   TO: X\_OUT\_OPHB4A\_4CT\_1
            -   ON CONDITION: if no error
        -   [ ] SET digital out
            -   FROM: DataPool / HMI
            -   TO: X\_OUT\_ODH4A\_4CT\_1
            -   ON CONDITION: if no error
        -   [ ] SET voltage setpoint
            -   FROM: DataPool / HMI
            -   TO: X\_UEXT\_ADJ\_5V\_12V\_1
            -   ON CONDITION: if no error
        -   [ ] GET voltage in
            -   FROM: X\_IN\_IDA35V\_1
            -   TO: DataPool / HMI
            -   ON CONDITION: if no error
        -   [ ] GET digital in
            -   FROM: X\_IN\_IDA35V\_2
            -   TO: DataPool / HMI
            -   ON CONDITION: if no error
        -   [ ] GET voltage in
            -   FROM: X\_IN\_IDA35V\_4
            -   TO: DataPool / HMI
            -   ON CONDITION: if no error
        -   [ ] CALC calibration offset correction
        -   [ ] CHECK for RESET message RX'd
            -   create a VALID flag
            -   execute a CAN RX
            -   Check for CAN RX is both VALID and contains RESET message (ie 0xEEu)
                -   if above is true, call RESET
    -   [ ] WHILE
        -   [ ] No RESET request RX'd
-   [ ] TERM TASK(s) <code>[0/0]</code>
    -   N/A.  No TERM tasks included in master model
-   [ ] FUNCTION DEFINITIONS <code>[0/4]</code>
    -   [ ] FUNC Change Color of LED
    -   [ ] FUNC Initialize CAN
    -   [ ] FUNC Initialize CAN TASK for ALIVE SIGNAL
    -   [ ] FUNC Send CAN ALIVE SIGNAL


<a id="org33a040a"></a>

## Model: C

(see above, Abstract)


<a id="orgb1a6692"></a>

## Model: IEC FBD


<a id="org376e781"></a>

### Program Flow & Checklist <code>[%]</code>

-   [ ] PREPROC <code>[0/0]</code>
-   [ ] INIT TASK(s) <code>[0/2]</code>
    -   [ ] COMMS <code>[0/9]</code>
        -   [ ] Initialize CAN
        -   [ ] Initialize Tx on CAN1
        -   [ ] Build Startup Tx MSG
        -   [ ] Initialize Rx on CAN1
        -   [ ] Start openSYDE Server
        -   [ ] Send Startup Tx MSG
        -   [ ] ?? 134 ??
        -   [ ] ?? Deadlock / ICC Safety Guard ??
        -   [ ] ?? LED physical debug INIT setup ??
    -   [ ] I/O <code>[0/7]</code>
        -   [ ] Initialize Uext (external voltage outpu)
        -   [ ] Allow usage of outputs via MainSwitch flag
        -   [ ] Initialize IO pwm\_output
        -   [ ] Initialize IO digital\_out
        -   [ ] Initialize IO voltage\_in
        -   [ ] Initialize IO digital\_in
        -   [ ] Initialize IO voltage\_in
-   [ ] CYCLIC TASK(s) <code>[0/2]</code>
    -   [ ] DO 
        -   [ ] SET pwm out
            -   FROM: DataPool / HMI
            -   TO: X\_OUT\_OPHB4A\_4CT\_1
            -   ON CONDITION: if no error
        -   [ ] SET digital out
            -   FROM: DataPool / HMI
            -   TO: X\_OUT\_ODH4A\_4CT\_1
            -   ON CONDITION: if no error
        -   [ ] SET voltage setpoint
            -   FROM: DataPool / HMI
            -   TO: X\_UEXT\_ADJ\_5V\_12V\_1
            -   ON CONDITION: if no error
        -   [ ] GET voltage in
            -   FROM: X\_IN\_IDA35V\_1
            -   TO: DataPool / HMI
            -   ON CONDITION: if no error
        -   [ ] GET digital in
            -   FROM: X\_IN\_IDA35V\_2
            -   TO: DataPool / HMI
            -   ON CONDITION: if no error
        -   [ ] GET voltage in
            -   FROM: X\_IN\_IDA35V\_4
            -   TO: DataPool / HMI
            -   ON CONDITION: if no error
        -   [ ] CALC calibration offset correction
        -   [ ] CHECK for RESET message RX'd
            -   create a VALID flag
            -   execute a CAN RX
            -   Check for CAN RX is both VALID and contains RESET message (ie 0xEEu)
                -   if above is true, call RESET
    -   [ ] WHILE
        -   [ ] No RESET request RX'd
-   [ ] TERM TASK(s) <code>[0/0]</code>
    -   N/A.  No TERM tasks included in master model
-   [ ] FUNCTION DEFINITIONS <code>[0/4]</code>
    -   [ ] FUNC Change Color of LED
    -   [ ] FUNC Initialize CAN
    -   [ ] FUNC Initialize CAN TASK for ALIVE SIGNAL
    -   [ ] FUNC Send CAN ALIVE SIGNAL


<a id="orge5a48a7"></a>

## Model: IEC ST


<a id="orgf9784e6"></a>

### Program Flow & Checklist <code>[%]</code>

-   [ ] PREPROC <code>[0/0]</code>
-   [ ] INIT TASK(s) <code>[0/2]</code>
    -   [ ] COMMS <code>[0/9]</code>
        -   [ ] Initialize CAN
        -   [ ] Initialize Tx on CAN1
        -   [ ] Build Startup Tx MSG
        -   [ ] Initialize Rx on CAN1
        -   [ ] Start openSYDE Server
        -   [ ] Send Startup Tx MSG
        -   [ ] ?? 134 ??
        -   [ ] ?? Deadlock / ICC Safety Guard ??
        -   [ ] ?? LED physical debug INIT setup ??
    -   [ ] I/O <code>[0/7]</code>
        -   [ ] Initialize Uext (external voltage outpu)
        -   [ ] Allow usage of outputs via MainSwitch flag
        -   [ ] Initialize IO pwm\_output
        -   [ ] Initialize IO digital\_out
        -   [ ] Initialize IO voltage\_in
        -   [ ] Initialize IO digital\_in
        -   [ ] Initialize IO voltage\_in
-   [ ] CYCLIC TASK(s) <code>[0/2]</code>
    -   [ ] DO 
        -   [ ] SET pwm out
            -   FROM: DataPool / HMI
            -   TO: X\_OUT\_OPHB4A\_4CT\_1
            -   ON CONDITION: if no error
        -   [ ] SET digital out
            -   FROM: DataPool / HMI
            -   TO: X\_OUT\_ODH4A\_4CT\_1
            -   ON CONDITION: if no error
        -   [ ] SET voltage setpoint
            -   FROM: DataPool / HMI
            -   TO: X\_UEXT\_ADJ\_5V\_12V\_1
            -   ON CONDITION: if no error
        -   [ ] GET voltage in
            -   FROM: X\_IN\_IDA35V\_1
            -   TO: DataPool / HMI
            -   ON CONDITION: if no error
        -   [ ] GET digital in
            -   FROM: X\_IN\_IDA35V\_2
            -   TO: DataPool / HMI
            -   ON CONDITION: if no error
        -   [ ] GET voltage in
            -   FROM: X\_IN\_IDA35V\_4
            -   TO: DataPool / HMI
            -   ON CONDITION: if no error
        -   [ ] CALC calibration offset correction
        -   [ ] CHECK for RESET message RX'd
            -   create a VALID flag
            -   execute a CAN RX
            -   Check for CAN RX is both VALID and contains RESET message (ie 0xEEu)
                -   if above is true, call RESET
    -   [ ] WHILE
        -   [ ] No RESET request RX'd
-   [ ] TERM TASK(s) <code>[0/0]</code>
    -   N/A.  No TERM tasks included in master model
-   [ ] FUNCTION DEFINITIONS <code>[0/4]</code>
    -   [ ] FUNC Change Color of LED
    -   [ ] FUNC Initialize CAN
    -   [ ] FUNC Initialize CAN TASK for ALIVE SIGNAL
    -   [ ] FUNC Send CAN ALIVE SIGNAL


<a id="orgdb78553"></a>

# Program Code

