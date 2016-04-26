# Which Signals A Process Accepts

Ever been curious which signals a process listens to and will respond to when sent? Under /proc/${PID}/status there are SigBlk (Signal Block), SigIgn (Signal Ignore) and SigCgt (Signal Caught) blocks.

  SigBlk:	7be3c0fe28014a03
  SigIgn:	0000000000001000
  SigCgt:	00000001800004ec

These are bitmasks that when convverted to binary reveal which signals are caught by the process based on position -> signal number.

  000000001800004ec --> 000000000000000000000000000000110000000000000000000010011101100
                                                      ||                    |  ||| ||
                                                      ||                    |  ||| |`-> 3,  SIGQUIT
                                                      ||                    |  ||| `--> 4,  SIGILL
                                                      ||                    |  ||`----> 6,  SIGABRT
                                                      ||                    |  |`-----> 7,  SIGBUS
                                                      ||                    |  `------> 8,  SIGFPE
                                                      ||                    `---------> 11, SIGSEGV
                                                      |`------------------------------> 32, SIGWAITING
                                                      `-------------------------------> 33, SIGLWP
