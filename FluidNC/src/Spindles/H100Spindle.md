H100 General protocol:

[id] [fcn code] [start addr] [payload] [checksum]

Read F011 (min frequency) and F005 (max frequency):

[01] [03] [000B] [0001] gives [03] [02] [xxxx] (with 02 the result byte count).
[01] [03] [0005] [0001] gives [03] [02] [xxxx] (with 02 the result byte count).

First commands. These give the identity response if things go correctly. So:

[01] [05] [00 49] [ff 00] [0c 2c] -- forward run
[01] [05] [00 4A] [ff 00] [0c 2c] -- reverse run
[01] [05] [00 4B] [ff 00] [0c 2c] -- stop

Tracking:
[01] [04] [0000] [0002] -- output frequency

Set frequency:
[01] [06] [0201] [07D0] Set frequency to [07D0] = 200.0 Hz. (2000 is written!)

Irrelevant but could be useful:
[01] [04] [0001] [0002] -- set frequency