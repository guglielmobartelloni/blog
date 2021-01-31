---
title:       "Mantenere la privacy nel Cloud"
subtitle:    ""
description: "Come tenere nascosti i vostri dati sul Cloud con GPG"
date:        2021-01-18
author:      "Guglielmo Bartelloni"
image:       ""
tags:        ["privacy cloud", "privacy", "cloud", "google drive privacy", "google drive", "gdrive privacy", "gdrive", "dropbox"]
categories:  ["Cose da Nerd" ]
---

# Motivazioni

Ormai si sa, la massoneria ci controlla, il Grande Fratello[^1] ci osserva!  Ogni cosa che facciamo, che guardiano, cosa ci piace.

La cosa divertente è che noi questi dati li diamo a *loro* di nostra spontanea volontà, quando decidiamo di usare i loro servizi. Sarà il fatto che questi servizi sono facili da usare ed il fatto che sono gratuiti, che ci porta ad utiizzarli.

Ma di fatto, in questo modo, ci stiamo spogliando di diritti che noi (o almeno i nostri antenati) ci siamo conquistati. Sembra un ciclo che si ripete: se l'uomo resta per un po' di tempo senza dover lottare, si addormenta sugli allori e diventa sempre più debole, tanto da diventare inerme di fronte alla privazione di certi diritti "scontati" come appunto quello della privacy. E poi arrivano le diddature, la gente si stufa, riprende la forza di lottare, la dittatura finisce e si ricomincia il giro. Del resto la storia si ripete...

Un'altra cosa interessante è il fatto che adesso, ogni qualvolta si entra su un sito, occorre sempre accettare quei cazzo di coockies (come da normativa), ma questo, non fa altro che abituare la gente a cliccare "Si accetto" ad ogni pop-up che si presenta davanti, quando in realtà i coockies potrebbero essere benissimo disattivati con 10 secondi in più di attenzione.

> Some might say "I don't care if they violate my privacy; I've got nothing to hide." Help them understand that they are misunderstanding the fundamental nature of human rights. Nobody needs to justify why they "need" a right: the burden of justification falls on the one seeking to infringe upon the right. But even if they did, you can't give away the rights of others because they're not useful to you. More simply, the majority cannot vote away the natural rights of the minority. [...] Arguing that you don't care about the right to privacy because you have nothing to hide is no different than saying you don't care about free speech because you have nothing to say. - [**Edward Snowden**](https://it.wikipedia.org/wiki/Edward_Snowden)

[^1]: George Orwell - 1984

Detto questo, direi di andare a vedere come quindi è possibile rendere illeggibili i file su Google Drive, Dropbox, OneDrive e chi più ne ha più ne metta...

# Soluzione

La soluzione che adotteremo è semplice: andremo a criptare i nostri file prima di caricarli sul Cloud. Ma come?

Esistono tanti applicativi che permettono di fare questo, io ho deciso di utilizzare [GPG (GNU Privacy Guard)](https://it.wikipedia.org/wiki/GNU_Privacy_Guard) perchè Open source, gratuito e utilizzatissimo.
Andremo ad usare il metodo di cifratura simmetrico in quanto in questo modo, basta che ci ricordiamo la password che impostiamo, senza essere costretti a spostare chiavi private ovunque vogliamo accedere ad i nostri file, inoltre come metodo di cifratura, quello simmettrico è molto più efficiente dell'asimmetrico quindi, ci quadagnamo anche da questo punto di vista.

Installiamo quindi GPG, a seconda del vostro sistema operativo chiaramente questa operazione sarà diversa. Io utilizzo arch linux (I use arch, btw) quindi per installarlo uso:

```js
sudo pacman -S gpg
```

ma comunque se usate linux dovrebbe essere preinstallato. Per Winzo...cioè Windows potete scaricarlo da [qua](https://gnupg.org/download/).
Per Android, scaricate [OpenKeychain](https://www.openkeychain.org/) disponibile anche su [F-Droid](https://f-droid.org/packages/org.sufficientlysecure.keychain/) per i più premurosi, vi spiegherò in seguito come usarlo. Per mac invece lo potete installare con homebrew:

```js
brew install gpg
```

Bene adesso facciamo un esempio con un file: voglio salvare sul Cloud un file chiamato "Banana", prima di fare l'upload apro il terminale e mi sposto nella cartella:

```js
cd frutta
```

Quindi eseguo la cifratura simmetrica del file col comando:

```js
gpg -c banana
```

Si presenterà una schermata che vi chiederaà di inserire la passphrase INSERIRE IMMAGEINE:


Inseritela e FATTO, nella cartella ci sarà un file chiamato nomefile.gpg, nel mio caso banana.gpg che potrete tranquillamente caricare sul cloud senza problemi.

## Cifrare file multipli

Ora vi starete chiedendo come uno possa caricare più di un file se lo volesse. Dobbiamo sostanzialmente trasformare i nostri file in un unico file, per farlo li inseriremo in un archivio compresso. Io userò tar ma voi potete usare quello che volete: 7zip, WinRAR...

Io con tar farò:

```js
tar -czvf banana.tar.gz cartellaConIFileMultipli
```

E quindi col comando precedente posso procedere a cifrare l'archivio.

## Decifratura

Per poter decifrare il file che avete caricato sul cloud potete eseguire il comando:


```js
gpg -d banana.gpg
```

Nella vostra cartella apparirà il file decifrato! INSERIRE MEME


## OpenKeyChain Android








