

# Summary


# Links / Resources


## Master Model (C)


### ESX-4CT\_Example.rtf


### ESX-4CT\_Example.syde


## IEC FBD Model


## IEC ST Model


# Model: Abstract


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


# Model: C

(see above, Abstract)


# Model: IEC FBD


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


# Model: IEC ST


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

