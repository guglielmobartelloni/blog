---
title:       "Come ho installato Mac OS sul mio Thinkpad x230"
subtitle:    ""
description: "Installazione di Mac OS con OpenCore"
date:        2021-01-17
author:      "Guglielmo Bartelloni"
image:       "/img/thinkpad-mac-os.png"
tags:        ["thinkpad x230", "Mac os", "thinkpad x230 mac os", "thnkpad mac os", "opencore", "thinkpad x230 opencore", "thinkpad opencore"]
categories:  ["Cose da nerd"]
---

## L'idea

Installare Mac OS è sempre stata una cosa che mi era passata per la mente ma, vuoi per il tempo, vuoi per la poca voglia di perderci le giornate, non avevo mai trasformato questi pensieri in realtà, fino a quando un giorno scopro [OpenCore](https://dortania.github.io/OpenCore-Install-Guide/) un progetto a dir poco stupefacente in grado di far girare Mac OS su gran parte dei PC in circolazione.

## Cosa funziona

Il sistema funziona sorprendentemente bene (come Cyberpunk 😜 ), ma non risulta essere veloce/immediato come Linux o Windows, certe ottimizzazioni riguardo al feeling sembrano mancare. Ciò che non funziona veramente è la scheda WIFI interna che non è supportata e quindi o la sostituite con una funzionante oppure fate come ho fatto io e vi comprate una scheda WIFI USB da 10€.

Un'altra cosa che non funziona e che, non ho trovato in giro come risolvere, sono le porte usb della docking station, non so se è un difetto della mia ma alcune porte sembrano non funzionare.

## Preparazione ⚙️

Innanzi tutto occorre precisare che ovviamente questa procedura potrebbe causare malfunzionamenti al vostro Thinkpad e/o danneggiare il vostro sistema, questa non vuole essere una guida per l'installazione quanto una minipanoramica su quello che mi sono trovato davanti durante l'installazione di Mac OS Catalina 10.5.

Detto questo iniziamo: mi sono basato sulla repository di [Github](https://github.com/banhbaoxamlan/X230-Hackintosh) resa disponibile da [bannhbaoxamlan](https://github.com/banhbaoxamlan) che ha messo a disposizione i file EFI per il corretto funzionamento del nostro thinkpad su Mac OS.

Come precisato dallo stesso utente, i file EFI funzionano per qualsiasi Thinkpad x230 indipendentemente dalla CPU a meno di avere un display modificato a 1440p (per questo vi è un workaround).

Occorrente:

- Una **chiavetta USB** vi consiglio di almeno 8GB, ma anche 4GB dovrebbero andare bene
- Pazienza, ve ne servirà credetemi
- Una banana 🍌, da degustare mentre il sistema viene installato 

## Pre-Installazione

### Preparazione della chiavetta USB

La procedura che ho seguito io su Windows (se siete su Linux seguite [questa](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/linux-install.html)) è stata [questa](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/winblows-install.html#downloading-macos) dove viene indicato per filo e per segno ciò che dovete fare per:

1. Scaricare Mac OS, vi consiglio Catalina 10.15 in quanto più stabile
2. Inserire il sistema di installazione nella chiavetta

Una volta che avete seguito la procedura inserite la cartella EFI della [repo](https://github.com/banhbaoxamlan/X230-Hackintosh) all'interno della root della chiavetta e sarete già pronti per installare il sistema 🎊.

Inserite la chiavetta nel Thinkpad e prima di fare il boot dalla chiavetta assicuratevi di avere le impostazioni del BIOS come seguono:

![Impostazioni del BIOS](/img/bios-settings.png)

Dopodichè fate il boot da chiavetta e scegliete la chiavetta per l'installazione del sistema guardando bene dal formattare il vostro disco con schema GUID tramite il disk utility.

Se avete dubbi nell'installazione seguite la [documentazione ufficiale](https://dortania.github.io/OpenCore-Install-Guide/installation/installation-process.html) che vi guiderà passo passo.

**Nota**: l'installazione impiega tanto tempo, si parla di 1h e passa, quindi non vi spaventate se ci mette tanto, nel frattempo potete degustare la vostra banana 🍌 .

## Post Install

Oltre a generare l'SMBIOS per il vostro Thinkapad Mac vi consiglio di installare [MountEFI](https://github.com/corpnewt/MountEFI) di modo da non dover richiedere la chiavetta USB ad ogni riavvio del sistema. Baseterà montare la partizione EFI sul disco di Mac OS e copiare la cartella EFI della chiavetta al suo interno.

Fatto questo, avete finito. Ora potete godervi il vostro Hackintosh, ed installare qualsiasi applicazione che volete. Io per esempio ho installato Logic per fare musica ed anche Final Cut, entrambi girano da DIO come da loro fama.

![logic](/img/logic-pro-x-thinkpad.png)
