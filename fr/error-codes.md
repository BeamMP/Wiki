---
title: Codes d'erreur & signification
description: Vous trouverez la liste des codes d'erreur du serveur du launcher et du jeu et leur signification Codes d'erreur & signification
published: true
date: 2022-12-22T09:23:17.645Z
tags: 
editor: markdown
dateCreated: 2021-04-22T12:05:34.390Z
---

> Si votre code d'erreur n'apparait pas sur cette page, vous pouvez vous referer à ce document https://docs.microsoft.com/en-us/windows/win32/winsock/windows-sockets-error-codes-2
{.is-warning}

# Codes d'erreur du launcher

> Note: Si le launcher s'arrête immédiatement vous pouvez vérifier le fichier log
{.is-info}

> Si le launcher bloque lors du téléchargement, vous pouvez essayer de le démarrer en mode administrateur. Parfois désactiver l'antivirus ou le pare-feu peut également aider
{.is-info}

`Code 2`
- Le processus qui a executé le launcher n'est plus valide, vous devriez essayer de démarrer le launcher sans utiliser de raccourci, directement dans le dossier d'installation

`Code 3`
- Le processus qui a executé le launcher est valide mais n'est pas un executable (.exe)

`Code 4`
- Le processus qui a executé le launcher est valide mais n'est pas l'explorateur ou une cmd

`Logger file init failed`
- Le launcher n'a pas la permission de créer de fichiers dans son dossier, démarrez le launcher en mode administrateur

`Sorry Backend System Outage! Don't worry it will back on soon!`
- La backend n'a pas répondue, cela peut parfois être dû au pare-feu ou à l'antivirus.

`Primary Servers Offline! sorry for the inconvenience!`
- Le launcher n'a pas réussi à vérifier les mises à jour, cela peut parfois être dû au pare-feu ou à l'antivirus.

`Launcher Update failed!`
- Le launcher n'a pas réussi à télécharger sa mise à jour

`Cannot Create BeamNG Directory! Retrying...`
- Le launcher n'a pas réussi à créer le dossier BeamNG Drive, ce dernier se relancera en mode administrateur après 3 secondes

`Please close the game and try again`
- Une instance du jeu est déjà en cours, cela est dû aux fichiers du jeu étant déjà utilisé par un autre processus. Vérifier que BeamNG.drive ou le launcher ne sont pas déjà ouvert

`Cannot Create Mods Directory! Retrying...`
- Le launcher n'a pas réussi à créer le dossier Mods, ce dernier se relancera en mode administrateur après 3 secondes

`Cannot Create Settings Directory! Retrying...`
- Le launcher n'a pas réussi à créer le dossier Settings, ce dernier se relancera en mode administrateur après 3 secondes

`Please launch the game at least once`
- Cela arrive lorsque le launcher essaye de modifier des fichiers qui n'ont pas été crées par le jeu. Lancer le jeu une fois puis le fermer devrait résoudre le problème

`Failed to launch the game`
- Cela arrive lorsque le launcher n'a pas réussi à modifier le dossier Profile, essayez de lancer en mode administrateur.

`Failed to Launch the game! launcher closing soon`
- Le launcher n'a pas réussi à démarrer le jeu, démarrer le jeu une fois puis le fermer devrait résoudre ce problème

`Game Closed! launcher closing soon`
- Cela arrive lorsque le jeu est fermé. Cela peut être dû à un bug du jeu ou si vous quitter simplement le jeu

`Mod did not load! launcher closing soon`
- Le mod BeamMP n'est pas chargé ni trouvé au bout de 35 secondes. Cela arrive lorsque BeamNG.drive est corrompu ou si l'utilisateur tente de modifier le mod

`Failed to find the game please launch it. Report this if the issue persists`
- Code 1 Le launcher n'a pas réussi à trouver le jeu dans Steam, un correctif potentiel serait de réinstaller le jeu ou de se mettre en mode EN LIGNE sur Steam
- Code 2 Voir Code 1
- Code 3 Le launcher n'a pas réussi à trouver les informations du jeu (dernier démarrage etc...)
- Code 4 Le launcher n'a pas réussi à ouvrir le fichier qui contient les informations du jeu, démarrer en administrateur pourrait résoudre le problème
- Code 5 Les fichiers du jeu n'ont pas été trouvés. Essayez de démarrer le jeu une fois puis de le fermer

`Sorry. We do not support cracked copies report this if you believe this is a mistake`
- Code 1 Le système a été trouvé mais pas son dossier d'installation, essayez de démarrer Steam ou de réinstaller Steam
- Code 2 l'identifiant du jeu n'a pas été trouvé dans le dossier Steam
- Code 3 le dossier du jeu n'a pas été trouvé dans Steam
- Code 4 Steam n'est pas installé ou n'a pas été trouvé
- Code 5 Le jeu n'a pas été trouvé dans le dossier steamapps, il pourrait avoir été déplacé manuellement
- Code 6 Le launcher n'a pas réussi à faire le lien entre l'identifiant Steam et l'identifiant Steam du jeu. Cela pourrait signifier que vous ne possédez pas le jeu

`Illegal steam modifications detected report this if you believe this is a mistake`
- Code 1 Des fichiers anormaux ont été trouvés dans le dossier Steam


# Autres codes d'erreur (Serveur et Launcher)

> Note: Si le launcher ou le serveur s'arrêtent immédiatement vous pouvez vérifier le fichier log
{.is-info}

`Code 10060`
- Il y un problème avec la redirection des ports. Vérifiez que vous avez redirigé vos ports correctement dans votre routeur

`Code 10022`
- Un problème est survenu lors de la tentative de démarrer sur le port. Le plus souvent ce problème est causé par un autre serveur ou un autre launcher déjà démarrés. Cela peut également être dû à un programme utilisant le même port que celui du launcher ou du serveur

`Code 10048`
- Le port est déjà en cours d'utilisation. Le plus souvent ce problème est causé par un autre serveur ou un autre launcher déjà démarrés. Cela peut également être dû à un programme utilisant le même port que celui du launcher ou du serveur

`Code 10051`
- Il y un problème avec la redirection des ports. Vérifiez que vous avez redirigé vos ports correctement dans votre routeur

`Code 10052`
- Une coupure réseau est survenue, essayez de redémarrer le launcher ou le serveur

`Code 10053`
- Erreur réseau inconnue, essayez de redémarrer le launcher ou le serveur

`Code 10054`
- Launcher: le serveur a été fermé
- Serveur: Client deconnecté

`Code 10060`
- Timeout du réseau, sur le launcher cela signifie souvent que les ports ont mal été redirigés

`Code 10061`
- Voir 10060

`Code 10064`
- Cette erreur est peu probable, elle peut être causée sur le launcher par (mais pas seulement) un crash du serveur ou si les ports ont été fermés lorsque la connection était déjà ouverte

`Code 10065`
- Impossible de joindre l'hôte de destination, cela peut être dû a une coupure internet ou une mauvaise redirection des ports