 

## Settings
How to set up lolMiner
1) Download the latest version of lolMiner
To run mining on multiple computers, download and install the lolMiner application on all computers that will be used for mining.
Unzip the downloaded one .zip archive and open it .bat file (batnik) in a text editor.
In the folder containing the miner, you must create or edit a file with the extension.bat. You can do this in any text editor (for example, in Notepad or Notepad ++). When saving a file, it is important to choose “All files” as the file type, not “txt”. Otherwise , you will have .bat.txt at the end of the file name, and the miner will not be able to open this file. Your bat file (let’s say it’s called Ethereum-finance_pool.bat) must contain the following text (step 2):

2) Enter the following command in the batnik:
setx GPU_FORCE_64BIT_PTR 0
setx GPU_MAX_HEAP_SIZE 100
setx GPU_USE_SYNC_OBJECTS 1
setx GPU_MAX_ALLOC_PERCENT 100
setx GPU_SINGLE_ALLOC_PERCENT 100
lolMiner.exe --algo ETHASH --pool ethash.poolbinance.com:8888 --user username1.worker_name --tls 0

3) Set up a miner for your wallet
WALLET_ADDRESS – enter YOUR Ethereum wallet address or the username of the pool – USERNAME, if there is registration on the pool (this way the program will understand where to send the extracted coins). WORKER_NAME is the name of your farm. You can choose any name (as a test), but don’t exaggerate: it should be no more than 32 characters maximum, contain only letters and numbers (without special characters such as $% “*; @). Don ‘t forget in all .bat files specify the address of your wallet!

4) Launch the miner
Double-click your Bat file to launch the miner. The miner will start, execute set commands to set environment variables, initialize each of your graphics cards, create a DAG file on each of your GPUs and start hashing. If you have completed the above steps, you should see a similar screen.


How to set up lolMiner with minerstat?
In this guide, we will show you how to set up BTCZ mining on lolMiner

1. Address editor
Open address editor and save the pool and wallet for mining BTCZ. Pool for mining BTCZ will be saved under (POOL:BTCZ) tag and wallet for mining BTCZ will be saved under (WALLET:BTCZ) tag.

2. Default mining client
Select LOLMINER as a default mining client in your worker’s config.

3. LOLMINER config
LOLMINER’s client’s configuration is defined as:{ “MINERSTAT” : { “DEVICES” : “AUTO”, “APIPORT” : 3333, “COIN” : “BTCZ”, “POOLS” : [ {“POOL” : “(POOL:BTCZ)“, “PORT” : “(AUTO)“, “USER” : “(WALLET:BTCZ).(WORKER)“, “PASS” : “x”} ] } }

The pool and wallet tags will be automatically replaced with the values you have entered in the first step in the address editor. (WORKER) tag will be automatically replaced with your worker’s name, so you don’t have to enter it manually.

Please note that lolMiner uses the parameter "COIN", which means that if you select any other coin aside of BTCZ, you will need to change this value as well. Otherwise the config won’t work.

4. Troubleshooting
To start saving logs for lolMiner, add the parameter "LOG" : 1 to your mining configuration.

5. Save changes
Save changes and wait for mining client to restart. You are now mining BTCZ with lolMiner.

lolMiner additional parameters
Running a mining program sometimes requires additional settings, for example, you need to disable one of the cards or set a limit on the operating temperature of the card. Below we have prepared for you a list of the most popular settings of the lolMiner miner. To apply the setting, add it to the standard startup line. Usually, the miner parameters cannot change the overclocking of the video card.

--tls starts mining via the TLS/SSL protocol. For mining over SSL, use the --tls on parameter. Note that usually the address of a pool with SSL is different from the address of a pool without SSL. Example eth.2miners.com:12020 — Ethereum pool 2Miners for SSL connection, eth.2miners.com:2020 — Ethereum pool 2Miners without SSL.

--devices allows you to use only the necessary video cards for mining. After —devices, specify the comma-separated indexes of those video cards that you want to use, while the first video card has an index of 0. For example, if you have a rig of 6 video cards, the video card indexes go from 0 to 5. Adding the --devices parameter 0,1,2,3,5 will start mining on all video cards except the fifth (with an index of 4). —devices can also be used to launch video cards of a certain manufacturer (only Nvidia or only AMD). So --nvidia devices will start mining only on Nvidia video cards.

--keepfree sets the memory value of the video card in MB, which cannot be used for mining purposes. The default value is 5 MB for Linux and 56 MB for Windows.

--tstart sets the minimum operating temperature of the video cards in °C. For example --tstart 30

--tstop sets the maximum operating temperature of the video cards in °C. For example --tstop 70

--the log parameter regulates the creation of a log file. --log on — the log file is created (it is by default), --log off — the log file is not created.

Skip back to main navigation
