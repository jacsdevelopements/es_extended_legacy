# es_extended_legacy
Le es_extended, version "Legacy", avec les doubles jobs. Le second job se nommant "job2".

Suivbant la même installation que le es_extended normal. Vous devez extraire le .rar. Un fichier es_extended apparaîtra. Vous devez l'insérer dans votre serveur,
comme ceci:

VotreServeur > resources > [esx] > es_extended

Une fois glissé dans le dossier [esx], vous rentrez dans le dossier [esx], puis dans es_extended, puis vous lancez le fichier es_extended.sql. Vous exécutez ce script SQL
dans votre base de données.

Une fois cela fait, vous allez dans votre server.cfg, et rajoutez ceci:

ensure es_extended

Vous devez rajouter cette ligne juste après ces lignes de commandes (que vous devriez voir dans votre server.cfg):

## Add system admins
add_ace group.admin command allow # allow all commands
add_ace group.admin command.quit deny # but don't allow quit
add_ace resource.es_extended command.add_ace allow
add_ace resource.es_extended command.add_principal allow
add_ace resource.es_extended command.remove_principal allow
add_ace resource.es_extended command.stop allow


Au final, vous avez ceci:

# # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # #
# ███████╗███████╗██╗  ██╗    ██╗     ███████╗ ██████╗  █████╗  ██████╗██╗   ██╗  #
# ██╔════╝██╔════╝╚██╗██╔╝    ██║     ██╔════╝██╔════╝ ██╔══██╗██╔════╝╚██╗ ██╔╝  #
# █████╗  ███████╗ ╚███╔╝     ██║     █████╗  ██║  ███╗███████║██║      ╚████╔╝   #
# ██╔══╝  ╚════██║ ██╔██╗     ██║     ██╔══╝  ██║   ██║██╔══██║██║       ╚██╔╝    #
# ███████╗███████║██╔╝ ██╗    ███████╗███████╗╚██████╔╝██║  ██║╚██████╗   ██║     #
# ╚══════╝╚══════╝╚═╝  ╚═╝    ╚══════╝╚══════╝ ╚═════╝ ╚═╝  ╚═╝ ╚═════╝   ╚═╝     #
# # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # # #
# Development Discord: https://discord.gg/k36Dnk3Kj6

# Changez cette IP en fonction de votre hébergeur (le port de celui-ci). Si vous êtes en localhost, ne changez rien.
endpoint_add_tcp "0.0.0.0:30120"
endpoint_add_udp "0.0.0.0:30120"


sv_hostname "Nom de votre serveur, qui apparaîtra dans la liste"
set steam_webApiKey ""
sv_licenseKey ""
sv_maxclients 10   # Choisissez le maximum de joueurs disponibles. Sans clé patréon achetée, vous pouvez mettre maximum 48 joueur.

sets sv_projectName "Nom de votre projet"
sets sv_projectDesc "Descirption de votre projet"
sets locale "fr-CA" # Langue de votre serveur, je l'ai mise déjà mise e nfrançais, ne pas toucher.
sets tags "tag1, tag2" # Tous les tags de votre serveur.
sv_scriptHookAllowed 0 #Ne pas toucher.

set onesync legacy   # Ne pas toucher.
set mysql_connection_string “server=127.0.0.01;database=NOMDEVOTREBASEDEDONEES;userid=root;” # Si vous êtes en localhost, remplacez simplement le "NOMDEVOTREBASEDEDONNEE, si vous êtes sur hébergeur, pensez également à changer l'IP, l'utilisateur et de rajouter password=MOTDEPASSE à la fin. Comme ceci: "server=127.0.0.01;database=NOMDEVOTREBASEDEDONEES;userid=root;password=MOTDEPASSE"


# Ressources par défaut.
ensure mapmanager
ensure chat
ensure spawnmanager
ensure sessionmanager

# Systèmes d'administrations, ne pas toucher.
add_ace group.admin command allow # allow all commands
add_ace group.admin command.quit deny # but don't allow quit
add_ace resource.es_extended command.add_ace allow
add_ace resource.es_extended command.add_principal allow
add_ace resource.es_extended command.remove_principal allow
add_ace resource.es_extended command.stop allow

# ESX Legacy
ensure es_extended


Si vous avez des questions, je vous invite à rejoindre mon serveur Discord de développement. Des améliorations et des mises à jours seont effectuées sur ce script.
ⓓⓘⓢⓒⓞⓡⓓ: https://discord.gg/k36Dnk3Kj6
