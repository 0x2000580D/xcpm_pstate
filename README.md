# xcpm_pstate
This is a demonstration on a way you can get CPU p-state distribution, turbo states, and the "active" package frequency on Intel Macs via `/dev/xcpm` (XNU CPU Power Manager). Sadly requires root because of ioctl though, also note that the xcpm is supposedly only available on Haswell or newer, but at this point it doesn't matter.

This originated from good ol' closed off powermetrics, which uses the xcpm for the CPU frequency metrics on Intel. At the time I was compelled to make this, I hadn't seen any other examples on how to do it, so I got it done after a little bit of digging around and reverse engineering. I think its cool!

You can build it with gcc or whatever to try, of course. Default sampling rate is 1s. Run with sudo. Here's an example from my MacBookPro11,1:
```
Max Efficient State: 3000 MHz
Non-Turbo States: 800-3000 MHz
Turbo States: 800-3500 MHz

Requested Distribution: 3500MHz: 3.86%  3400MHz: 0.00%  3300MHz: 0.00%  3200MHz: 5.75%  3100MHz: 0.00%  3000MHz: 31.20%  2900MHz: 0.00%  2800MHz: 0.00%  2700MHz: 0.00%  2600MHz: 0.00%  2500MHz: 0.00%  2400MHz: 0.00%  2300MHz: 0.00%  2200MHz: 0.00%  2100MHz: 0.00%  2000MHz: 0.00%  1900MHz: 52.27%  1800MHz: 0.00%  1700MHz: 0.00%  1600MHz: 0.00%  1500MHz: 0.00%  1400MHz: 0.00%  1300MHz: 0.00%  1200MHz: 0.00%  1100MHz: 0.00%  1000MHz: 0.00%  900MHz: 0.00%  800MHz: 6.91%  

Requested Package Frequency: 2303.75 MHz
```
