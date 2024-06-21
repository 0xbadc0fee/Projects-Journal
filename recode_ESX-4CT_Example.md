
# Table of Contents

1.  [Summary](#org99938f6)
2.  [Links / Resources](#orgf648d84)
    1.  [Master Model (C)](#orgf119ff2)
        1.  [ESX-4CT<sub>Example.rtf</sub>](#org18ccbcb)
        2.  [ESX-4CT<sub>Example.syde</sub>](#org0b73ce0)
    2.  [IEC FBD Model](#org91fdc7a)
    3.  [IEC ST Model](#orgb5f458e)
3.  [Model: Abstract](#org59e1f71)
    1.  [Top-Down Program Flow & Checklist <code>[0%]</code>](#org1216b67)
4.  [Model: C](#orgd495a6c)
5.  [Model: IEC FBD](#org7fca4e9)
    1.  [Program Flow & Checklist <code>[%]</code>](#org81b0650)
6.  [Model: IEC ST](#orgd6660a3)
    1.  [Program Flow & Checklist <code>[%]</code>](#org7e6f692)



<a id="org99938f6"></a>

# Summary


<a id="orgf648d84"></a>

# Links / Resources


<a id="orgf119ff2"></a>

## Master Model (C)


<a id="org18ccbcb"></a>

### ESX-4CT<sub>Example.rtf</sub>


<a id="org0b73ce0"></a>

### ESX-4CT<sub>Example.syde</sub>


<a id="org91fdc7a"></a>

## IEC FBD Model


<a id="orgb5f458e"></a>

## IEC ST Model


<a id="org59e1f71"></a>

# Model: Abstract


<a id="org1216b67"></a>

## Top-Down Program Flow & Checklist <code>[0%]</code>

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
        -   [ ] Initialize IO pwm<sub>output</sub>
        -   [ ] Initialize IO digital<sub>out</sub>
        -   [ ] Initialize IO voltage<sub>in</sub>
        -   [ ] Initialize IO digital<sub>in</sub>
        -   [ ] Initialize IO voltage<sub>in</sub>
-   [ ] CYCLIC TASK(s) <code>[0/2]</code>
    -   [ ] DO 
        -   [ ] SET pwm out
            -   FROM: DataPool / HMI
            -   TO: X<sub>OUT</sub><sub>OPHB4A</sub><sub>4CT</sub><sub>1</sub>
            -   ON CONDITION: if no error
        -   [ ] SET digital out
            -   FROM: DataPool / HMI
            -   TO: X<sub>OUT</sub><sub>ODH4A</sub><sub>4CT</sub><sub>1</sub>
            -   ON CONDITION: if no error
        -   [ ] SET voltage setpoint
            -   FROM: DataPool / HMI
            -   TO: X<sub>UEXT</sub><sub>ADJ</sub><sub>5V</sub><sub>12V</sub><sub>1</sub>
            -   ON CONDITION: if no error
        -   [ ] GET voltage in
            -   FROM: X<sub>IN</sub><sub>IDA35V</sub><sub>1</sub>
            -   TO: DataPool / HMI
            -   ON CONDITION: if no error
        -   [ ] GET digital in
            -   FROM: X<sub>IN</sub><sub>IDA35V</sub><sub>2</sub>
            -   TO: DataPool / HMI
            -   ON CONDITION: if no error
        -   [ ] GET voltage in
            -   FROM: X<sub>IN</sub><sub>IDA35V</sub><sub>4</sub>
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


<a id="orgd495a6c"></a>

# Model: C

(see above, Abstract)


<a id="org7fca4e9"></a>

# Model: IEC FBD


<a id="org81b0650"></a>

## Program Flow & Checklist <code>[%]</code>

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
        -   [ ] Initialize IO pwm<sub>output</sub>
        -   [ ] Initialize IO digital<sub>out</sub>
        -   [ ] Initialize IO voltage<sub>in</sub>
        -   [ ] Initialize IO digital<sub>in</sub>
        -   [ ] Initialize IO voltage<sub>in</sub>
-   [ ] CYCLIC TASK(s) <code>[0/2]</code>
    -   [ ] DO 
        -   [ ] SET pwm out
            -   FROM: DataPool / HMI
            -   TO: X<sub>OUT</sub><sub>OPHB4A</sub><sub>4CT</sub><sub>1</sub>
            -   ON CONDITION: if no error
        -   [ ] SET digital out
            -   FROM: DataPool / HMI
            -   TO: X<sub>OUT</sub><sub>ODH4A</sub><sub>4CT</sub><sub>1</sub>
            -   ON CONDITION: if no error
        -   [ ] SET voltage setpoint
            -   FROM: DataPool / HMI
            -   TO: X<sub>UEXT</sub><sub>ADJ</sub><sub>5V</sub><sub>12V</sub><sub>1</sub>
            -   ON CONDITION: if no error
        -   [ ] GET voltage in
            -   FROM: X<sub>IN</sub><sub>IDA35V</sub><sub>1</sub>
            -   TO: DataPool / HMI
            -   ON CONDITION: if no error
        -   [ ] GET digital in
            -   FROM: X<sub>IN</sub><sub>IDA35V</sub><sub>2</sub>
            -   TO: DataPool / HMI
            -   ON CONDITION: if no error
        -   [ ] GET voltage in
            -   FROM: X<sub>IN</sub><sub>IDA35V</sub><sub>4</sub>
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


<a id="orgd6660a3"></a>

# Model: IEC ST


<a id="org7e6f692"></a>

## Program Flow & Checklist <code>[%]</code>

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
        -   [ ] Initialize IO pwm<sub>output</sub>
        -   [ ] Initialize IO digital<sub>out</sub>
        -   [ ] Initialize IO voltage<sub>in</sub>
        -   [ ] Initialize IO digital<sub>in</sub>
        -   [ ] Initialize IO voltage<sub>in</sub>
-   [ ] CYCLIC TASK(s) <code>[0/2]</code>
    -   [ ] DO 
        -   [ ] SET pwm out
            -   FROM: DataPool / HMI
            -   TO: X<sub>OUT</sub><sub>OPHB4A</sub><sub>4CT</sub><sub>1</sub>
            -   ON CONDITION: if no error
        -   [ ] SET digital out
            -   FROM: DataPool / HMI
            -   TO: X<sub>OUT</sub><sub>ODH4A</sub><sub>4CT</sub><sub>1</sub>
            -   ON CONDITION: if no error
        -   [ ] SET voltage setpoint
            -   FROM: DataPool / HMI
            -   TO: X<sub>UEXT</sub><sub>ADJ</sub><sub>5V</sub><sub>12V</sub><sub>1</sub>
            -   ON CONDITION: if no error
        -   [ ] GET voltage in
            -   FROM: X<sub>IN</sub><sub>IDA35V</sub><sub>1</sub>
            -   TO: DataPool / HMI
            -   ON CONDITION: if no error
        -   [ ] GET digital in
            -   FROM: X<sub>IN</sub><sub>IDA35V</sub><sub>2</sub>
            -   TO: DataPool / HMI
            -   ON CONDITION: if no error
        -   [ ] GET voltage in
            -   FROM: X<sub>IN</sub><sub>IDA35V</sub><sub>4</sub>
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

