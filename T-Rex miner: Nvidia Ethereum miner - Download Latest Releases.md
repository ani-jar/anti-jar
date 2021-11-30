Overview
T-Rex is a versatile cryptocurrency mining software. It supports a variety of algorithms and we, as developers, are trying to do our best to make it as fast and as convenient to use as possible.

Developer fee is 1% (2% for Octopus, Autolykos2, and their dual mining modes).

Download T-Rex for Windows
Download T-Rex for Linux
JSON config file
To start T-Rex with config file config.txt type in the console: t-rex -c config.txt. Use config_example file as a starting point to create your own config.
If a parameter is set in the config file and also via cmd line, the latter takes precedence, for example: t-rex -c config.txt -w <worker_name_to_override_the_one_in_config_file>
You can also use environment variables: simply put %YOUR_ENV_VAR% anywhere in your config file and it will get automatically substituted with the value of YOUR_ENV_VAR variable at run-time.

Watchdog
Watchdog is intended to observe miner state and restart T-Rex if it crashes or hangs for any reason. Also, watchdog can optionally perform auto updates if a newer version is available. We recommend using the watchdog to avoid any downtime in mining and make sure your GPUs are busy 24/7. If you do need to disable the watchdog, you can do so using --no-watchdog parameter.

Antivirus alerts
In order to protect the miner from reverse engineering attacks, the binaries are packed using a third-party software which mangles the original machine code. As a result, some antivirus engines may detect certain signatures within the executable that are similar to those that real viruses protected by the same packer have. In any case, it is advisable not to use cryptocurrency miners on the computers where you store your sensitive data (wallets, passwords etc.).

Tips
In order to maximise the hashrate our software utilises all available GPU resources, so it is important that you review your overclock settings before you start mining. Our general recommendation is to start from GPU stock settings (no overclock, default power limit), and then after making sure it is stable, slowly increase your overclock to find the “sweet spot” where the miner performs at its best and still does not crash.

HOW TO MINE ETHEREUM | WINDOWS | W/ T-REX 2020

Supported Algorithm:
On the right is a list of algorithms supported by the T-Rex mining program (miner). The program commission is shown for each of the algorithms. This commission usually does not exceed a few percent and is used by the developers of the miner to maintain and improve its work, as well as to add new functions. The commission is taken due to the fact that the program mines a short period of time (usually no more than a minute) every hour to the developer’s wallet.

Algorithm	Fee %
Ethash	1.0
Etchash	1.0
Octopus	2.0
Kawpow	1.0
Mtp	1.0
Mtp-tcr	1.0
Multi	1.5
Progpow	1.0
Progpowz	1.0
Progpow-veriblock	1.0
Progpow-veil	1.0
Tensority	1.0
Change log:
T-Rex v0.24.7

Bug fixes:

Some command line arguments don’t take precedence over the values set in a config file (e.g. --lhr-autotune-step-size)
(WebUI) Performance degradation introduced in 0.24.6
(WebUI) Monitoring page shows a blank page if you had 15M or 2H graph views selected while using an older version of T-Rex
(WebUI) Impossible to set LHR tune values with decimal point
HiveOS users: many of you complained that your hashrate on LHR cards is fluctuating too much compared to the Windows version. The reason is HiveOS sets "hashrate-avr": 30 for T-Rex causing it to report 30-seconds average hashrate as opposed to 1-minute average (default).
A temporary solution would be to edit your flight sheet and manually add "hashrate-avr": 60 to the “Extra config arguments” field. Otherwise, we’ve been told there will be a HiveOS release that fixes it permanently.

T-Rex v0.24.6

(ethash) Improve LHR unlocker, LHR tune value increased from 71 to 74 by default.
The new LHR tune scale is somewhat different, so it’s recommended to let autotune find the optimal parameters
(in other words, for the first run, remove --lhr-autotune-mode and --lhr-tune parameters from your bat file if they are set)
(ethash, autolykos2) New --lhr-autotune-step-size and --lhr-autotune-interval parameters for finer control of LHR unlock behaviour
(ethash, firopow) Add ETH+FIRO dual mining (use the same OC settings as ETH+RVN)
(autolykos2) New --dataset-mode parameter to enable/disable double buffer mode: 1 – single buffer mode, 2 – double buffer mode (default)
Add SOCKS5 proxy support (see --proxy parameter)
New --temperature-color-mem parameter to control memory temperature highlighting in console and WebUI
(WebUI) Multiple improvements:
24H view on the graph
Ability to hide individual charts (power, avg hashrate etc.) on the graph
Recompute average hashrate/power when zooming in the graph
Ability to reorder/hide GPU table columns
Auto-propagation of the miner node list to all nodes
Bug fixes:

(ethash) RTX 3060 GA104 is not recognised as an LHR card
Veriblock mining is broken since 0.24.2
(Linux) Log file contains ANSI escape sequences
(WebUI) Log file retrieved through WebUI has trailing zeros
Known issues: WebUI shows a blank page if you had 15M or 2H graph views selected on the previous version. Temporary solution is to delete browser cookies.

T-Rex v0.24.5

Bug fixes:

(autolykos2) Double-buffer feature in 0.24.4 is not activated automatically unless --lhr-tune is specified
T-Rex v0.24.4

(autolykos2) Increase pool-side hashrate by 1-4%.
The miner now generates the dataset for the next ERGO block before it arrives with a small penalty to reported hashrate, and when the next block does arrive, it immediately starts hashing without losing 1-4 seconds on creating the dataset.
Memory requirements are doubled in this mode as the GPU has to hold two memory buffers. If there is not enough memory on the GPU for two datasets, the miner will fall back to running in single buffer mode.
To take the full advantage of this mode it’s recommended not to set power limit but instead limit power consumption with --lock-cclock – this will allow the miner to draw more power during dataset rebuild and not lose hashrate. If you prefer to keep your power consumption constant, you can still set the power limit, however, in that case you’ll notice a slight hashrate drop after each block.
Please note that in both cases the miner should give you higher pool-side hashrate in the long run compared to previous versions. Miner’s reported hashrate now fully accounts for dataset creation time.
(kawpow, firopow) Report hashrate to the mining pool
(WebUI) Add support for displaying multiple rigs (nodes) on the same page; various improvements and fixes
Add --devices-info parameter to list available CUDA devices
Bug fixes:

(ethash, autolykos2) LHR lock detection is triggered by short-term hashrate drops, e.g. when turning on the monitor connected to the GPU.
Original overclock settings are not restored upon miner shutdown in dual mining mode (only applicable if you overclock GPUs with t-rex)
(WebUI) Cannot set --gpu-report-interval to 0 (disable)
(WebUI, API) GPUs are sometimes paused with a considerable delay (should be immediate)
