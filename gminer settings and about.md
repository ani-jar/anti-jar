ABOUT US:
GMiner was created by a Russian group of specialists in the field of high performance computing and cryptography.
The first version of GMiner was released on September 21, 2018 and was received quite warmly among users.
Thanks to its unique developments and stability, in just six months, the miner became a favorite on the Equihash algorithms.
The miner is focused on NVIDIA and AMD platforms and supports most popular algorithms such as: Ethash, ProgPoW, KAWPOW, Equihash, CuckooCycle.
GMiner maintains a leading position in the mining of such coins as Beam, Grin, Cortex, Bitcoin Gold.
In 2020, the miner added support for Ethash, ProgPoW and KAWPOW algorithms with high performance relative to competitors.
The development team never stops at what has been achieved and achieves the maximum performance of the algorithms with the minimum power consumption, it is these qualities that distinguish GMiner from the competitors and win the hearts of users.


MINER FEATURES:
commission is charged continuously, and not in intervals (as in most miners), which has a positive effect on the user’s profitability on PPLNS pools
verifying generated DAG, warning when GPU overclocking is very high for Ethash, Etcash, KAWPOW and ProgPoW algorithms, helps to overclock GPU without errors
verifying Shares on processor, warning when GPU overclocking is very high for Ethash, Etcash, KAWPOW and ProgPoW algorithms, helps to overclock GPU without errors
DAG caching if the GPU has enough memory, DAG files are not recomputed when switching to another algorithm when mining Ethash + Zilliqa or Nicehash, which has a positive effect on user profitability
auto selection of optimal kernels for each device on Ethash, Etcash, KAWPOW
ability to manually select kernel on each device for Ethash, Etcash
temperature control and stop the GPU in case of overheating
watchdog – process-observer of state of main systems of the miner, which will restart the miner in case of crash or freeze
mechanism to restore lost connection with pool
supporting failover pools, the miner uses failover pools until the connection with the main pool is restored
support secure connections
support SOCKS5 proxy
informative and readable tabular statistics output to console
display of detailed information on each device (temperature, power consumption, cooler load, memory frequency, processor frequency, energy efficiency)
parallel output of information to console and to file on disk
built-in statistics server – remote monitoring of the miner in browser
memory tweaks for Nvidia GPUs with GDDR5X and GDDR5 memory
core clocks, memory clocks, core voltage, memory voltage, fan speed, power limit overclocking for Windows
safe DAG generation for Nvidia GPUs
automatic fan speed control for target temperature
SUPPORTED ALGORITHMS AND DEVELOPER COMMISSION:

Algorithm	Fee
eth, ethash	0.65%
etc, etchash	0.65%
kawpow, rvn, ravencoin	1%
cortex	5%
beamhash	2%
equihash144_5	2%
equihash125_4	2%
equihash192_7	2%
equihash210_9	2%
cuckoo29, aeternity	2%
HOW TO MINE ETHEREUM WITH GMINER POOL ETHERMINE WALLET EXODUS:

RELEASES (CHANGE LOG):
GMiner v2.73

added LHR mode support for RTX 3060 GA104
added option to control LHR tune step size (–lhr_autotune_step)
added watchdog mode: reboot system or restart miner (–watchdog_mode)
added option to observe rig speed, miner quits if average speed reached limit (–min_rig_speed)
added option to control maximal number of parallel DAG generations (–dag_gen_limit)
display IP address of pool in statistics report
restore overclocking after stopping of mining
GMiner v2.72

fixed memory leaks on AMD GPUs
fixed compatibility with latest linux distributions
fixed crashes appeared in v2.71
GMiner v2.71

Improved LHR performance, added two modes (–lhr_mode): 0 – energy save mode, 1 – maximal performance mode (default).
Miner display LHR unlock percentage in statistics table (LHR row), you can adjust it by –lhr_tune option.
Now –lhr_tune meaning GPU unlock percentage, for compatibility lhr tunes below 10 mapped to new default values.
If LHR auto-tune (–lhr_autotune) enabled miner tries increase LHR unlock percentage while mining.
Improved RavenCoin performance, fixed floating hashrate
Display maximum difficulty of shares for each GPU
GMiner v2.70

improved auto-tune for LHR GPUs, now miner speedup performance when GPU is steady
removed –lhr_tune1 / –lhr_tune2 parameters, use –lhr_tune to tune LHR GPUs (value range is -10 – 10, old parameters ignored for compatibility)
display current –lhr_tune value and current kernel in statistics table
GMiner v2.69

added auto-tune for LHR GPUs (enabled by default, to disable pass –lhr_autotune 0)
fixed RavenCoin support under Windows 7
increased reconnect tries on connection loss (–reconnect_count)
improved miner stability
