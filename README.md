## Prerequisite :
* [Golang](https://golang.org/) : Used to compile the code
* [Git](https://git-scm.com/) : Used to retrieve the code from Github
* [GnuWin32](https://sourceforge.net/projects/gnuwin32/files/make/3.81/make-3.81.exe/download): Used for the makefile

### Optional :
* [CMDer](https://cmder.net/) : better terminal for Windows (includes Git)

## Step by step tutorial
1. Use `cd` to go to the desired location for the program, *e.g.* `cd E:\Users\Quentin\Documents\Programmation\Go`
2. Clone the repository here : `git clone https://github.com/streambinder/spotitube.git`
3. Set the GOPATH variable to the code folder location, *e.g.* `SET GOPATH=E:\Users\Quentin\Documents\Programmation\Go\spotitube`
4. Now, there's a bunch of libraries to download. You can copy and paste all of this into your terminal, this should download everything needed (else, copy, paste and execute each line after another) :
```
go get github.com\0xAX\notificator
go get github.com\PuerkitoBio\goquery
go get github.com\agnivade\levenshtein
go get github.com\bogem\id3v2
go get github.com\bradfitz\slice
go get github.com\fatih\color
go get github.com\jroimartin\gocui
go get github.com\kennygrant\sanitize
go get github.com\lunixbochs\vtclean
go get github.com\mozillazg\go-unidecode
go get github.com\zmb3\spotify
```
5. **WARNING: ASK ME FOR THE KEYS BEFORE DOING THIS STEP**. Now, use the GnuWin32 `make` tool to build the project, e.g. `"c:\Program Files (x86)\GnuWin32\bin\make.exe" SPOTIFY_ID=SPOTIFYAPIID SPOTIFY_KEY=SPOTIFYSECRETAPIKEY` (while you're in the `spotitude` root folder). You MUST specify the API keys. This should generate an `out/` folder
6. In the `out/` folder, rename `spotitube`to `spotitube.exe`
7. Go to https://ytdl-org.github.io/youtube-dl/download.html, download the **Windows exe** and put it into the `spotitube/out/` folder
8. Go to https://ffmpeg.zeranoe.com/builds/ and download the **SHARED** library (select **Shared** in the **Linking** column, to the right). Open the archive, go into the `bin/` folder, and copy/paste everything into the `spotitube/out/` folder
9. You're almost there. Now go on Spotify, and find a playlist you want to export. Right click on it, then go to **share**, then **copy Spotify URI**
10. Now, launch the exe with your terminal, specifying the playlist argument (paste the **Spotify URI**). You must also add `-disable-gui` and `-disable-browser-opening` e.g. `spotitube.exe -playlist spotify:user:coulis:playlist:4DpcZ6Wfs3mzzwsnaXmN3L -disable-gui -disable-browser-opening`
11. Once you've done this, the program will launch, and stop at the `Authentication URL:` line. Copy the URL, and paste it into your browser. Allow the access, and the download should start
