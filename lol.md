Это версия страницы https://lolminer.nz/fr/parametre/ из кеша Google. Она представляет собой снимок страницы по состоянию на 23 ноя 2021 15:25:58 GMT. Текущая страница за прошедшее время могла измениться. Подробнее.
Полная версияТекстовая версияПросмотреть исходный код
Совет. Чтобы искать на странице, нажмите Ctrl+F или ⌘-F (для MacOS) и введите запрос в поле поиска.
Skip to main navigationSkip to main contentSkip to footer

Rechercher : 
Search…
  

lolMiner
Principale
Paramètre
Français
English
Русский
Français
lolMiner
 Mobile Menu
Paramètre
Comment configurer lolMiner
1) Téléchargez la dernière version de lolMiner
Pour exécuter le minage sur plusieurs ordinateurs, téléchargez et installez l’application lolMiner sur tous les ordinateurs qui seront utilisés pour le minage.
Décompressez l’archive .zip téléchargée et ouvrez-la le fichier .bat (batnik) dans un éditeur de texte.
Dans le dossier contenant le mineur, vous devez créer ou éditer un fichier avec l’extension.bat. Vous pouvez le faire dans n’importe quel éditeur de texte (par exemple, dans le Bloc-notes ou le Bloc-notes ++). Lors de l’enregistrement d’un fichier, il est important de choisir « Tous les fichiers » comme type de fichier, et non « txt ». Sinon, vous aurez .bat.txt à la fin du nom du fichier, et le mineur ne pourra pas ouvrir ce fichier. Votre fichier bat (disons qu’il s’appelle Ethereum-finance_pool.bat) doit contenir le texte suivant (étape 2) :

2) Entrez la commande suivante dans le batnik :
setx GPU_FORCE_64BIT_PTR 0
setx GPU_MAX_HEAP_SIZE 100
setx GPU_USE_SYNC_OBJECTS 1
setx GPU_MAX_ALLOC_PERCENT 100
setx GPU_SINGLE_ALLOC_PERCENT 100
lolMiner.exe --algo ETHASH --pool ethash.poolbinance.com:8888 --user username1.worker_name --tls 0

3) Configurez un mineur pour votre portefeuille
WALLET_ADDRESS– entrez l’ YOURadresse du portefeuille Ethereum ou le nom d’utilisateur du pool – USERNAME, s’il y a une inscription sur le pool (de cette façon, le programme comprendra où envoyer les pièces extraites). WORKER_NAMEest le nom de votre ferme. Vous pouvez choisir n’importe quel nom (à titre de test), mais n’exagérez pas : il ne doit pas dépasser 32 caractères maximum, ne contenir que des lettres et des chiffres (sans caractères spéciaux tels que $% « *; @). N’oubliez pas dans tous les fichiers .bat de préciser l’adresse de votre wallet !

4) Lancer le mineur
Double-cliquez your Bat filepour lancer le mineur. Le mineur démarrera, exécutera les commandes set pour définir les variables d’environnement, initialisera chacune de vos cartes graphiques, créera un fichier DAG sur chacun de vos GPU et commencera le hachage. Si vous avez terminé les étapes ci-dessus, vous devriez voir un écran similaire.


Comment configurer lolMiner avec minerstat ?
Dans ce guide, nous allons vous montrer comment configurer le minage BTCZ sur lolMiner

1. Éditeur d’adresses
Ouvrez l’éditeur d’adresses et enregistrez le pool et le portefeuille pour l’extraction de BTCZ. Le pool pour l’exploitation minière BTCZ sera enregistré sous (POOL:BTCZ) l’étiquette et le portefeuille pour l’exploitation minière BTCZ seront enregistrés sous (WALLET:BTCZ) étiqueter.

2. Client minier par défaut
Sélectionnez  LOLMNER  comme client de minage par défaut dans la configuration de votre travailleur.

3. Configuration LOLMNER
La configuration du client LOLMINER est définie comme :{ « MINERSTAT » : { « DEVICES » : « AUTO », « APIPORT » : 3333, « COIN » : « BTCZ », « POOLS » : [ {« POOL » : « (POOL:BTCZ)« , « PORT » : « (AUTO)« ,  » UTILISATEUR  » :  » « ,  » PASS  » :  » x « } ] } }(WALLET:BTCZ).(WORKER)

Les balises pool et wallet seront automatiquement remplacées par les valeurs que vous avez saisies lors de la première étape dans l’éditeur d’adresses. (WORKER) tag sera automatiquement remplacé par le nom de votre travailleur, vous n’avez donc pas besoin de le saisir manuellement.

Veuillez noter que lolMiner utilise le paramètre  "COIN", ce qui signifie que si vous sélectionnez une autre pièce en dehors de BTCZ, vous devrez également modifier cette valeur. Sinon la configuration ne fonctionnera pas.

4. Dépannage
Pour commencer à enregistrer les journaux pour lolMiner, ajoutez le paramètre  "LOG" : 1 à votre configuration d’exploration de données.

5. Enregistrer les modifications
Enregistrez les modifications et attendez que le client de minage redémarre. Vous exploitez maintenant BTCZ avec lolMiner.

lolMiner paramètres supplémentaires
L’exécution d’un programme de minage nécessite parfois des paramètres supplémentaires, par exemple, vous devez désactiver l’une des cartes ou définir une limite sur la température de fonctionnement de la carte. Ci-dessous, nous avons préparé pour vous une liste des paramètres les plus populaires du mineur lolMiner. Pour appliquer le paramètre, ajoutez-le à la ligne de démarrage standard. Habituellement, les paramètres du mineur ne peuvent pas modifier l’overclocking de la carte vidéo.

--tls commence le minage via le protocole TLS/SSL. Pour l’exploration sur SSL, utilisez  --tls le paramètre on. Notez que généralement l’adresse d’un pool avec SSL est différente de l’adresse d’un pool sans SSL. Exemple eth.2miners.com:12020 — Ethereum pool 2Miners pour connexion SSL, eth.2miners.com:2020 — Ethereum pool 2Miners sans SSL.

--devices vous permet d’utiliser uniquement les cartes vidéo nécessaires pour l’exploitation minière. Après —périphériques, spécifiez les index séparés par des virgules de ces cartes vidéo que vous souhaitez utiliser, tandis que la première carte vidéo a un index de 0. Par exemple, si vous avez une plate-forme de 6 cartes vidéo, les index de la carte vidéo vont de 0 à 5. L’ajout de  --devices parameter 0,1,2,3,5 commencera à miner sur toutes les cartes vidéo sauf la cinquième (avec un indice de 4). —les appareils peuvent également être utilisés pour lancer les cartes vidéo d’un certain fabricant (uniquement Nvidia ou uniquement AMD). Alors  --nvidia devices commencera à miner uniquement sur les cartes vidéo Nvidia.

--keepfree définit la valeur de mémoire de la carte vidéo en Mo, qui ne peut pas être utilisée à des fins de minage. La valeur par défaut est de 5 Mo pour Linux et de 56 Mo pour Windows.

--tstart règle la température minimale de fonctionnement des cartes vidéo en °C. Par exemple --tstart 30

--tstop règle la température maximale de fonctionnement des cartes vidéo en °C. Par exemple --tstop 70

--the log paramètre régule la création d’un fichier journal. --log on — le fichier journal est créé (il l’est par défaut),  --log off — le fichier journal n’est pas créé.

Skip back to main navigation
