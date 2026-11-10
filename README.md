# Stashbox 1.0.1

Stashbox is a private media library that runs on your own computer. It finds your videos, matches them
with StashDB (performers, studios, titles) and TMDB (movies), and lets you browse, search and watch
them in a clean app, on that computer or on any phone, tablet or TV on your home network. It can also
find and download new releases for you and sort them into your library automatically.

Everything runs on your machine. Your library, watch history and settings stay with you.

---

## Contents

1. [What you get](#1-what-you-get)
2. [Requirements](#2-requirements)
3. [Install](#3-install)
4. [First-time setup](#4-first-time-setup)
5. [Finding your way around](#5-finding-your-way-around)
6. [Scanning your library](#6-scanning-your-library)
7. [Watching](#7-watching)
8. [Getting new content](#8-getting-new-content)
9. [Fixing matches, tags and collections](#9-fixing-matches-tags-and-collections)
10. [Maintenance](#10-maintenance)
11. [Watching on other devices](#11-watching-on-other-devices)
12. [Where things are stored](#12-where-things-are-stored)
13. [Network drives](#13-network-drives)
14. [Backup, update and uninstall](#14-backup-update-and-uninstall)
15. [Troubleshooting](#15-troubleshooting)
16. [Privacy and security](#16-privacy-and-security)
17. [Responsible use](#17-responsible-use)
18. [Included software and licences](#18-included-software-and-licences)

---

## 1. What you get

One installer sets up everything Stashbox needs. You do not install anything else yourself.

| Part | What it does |
| --- | --- |
| **Stashbox** | The app: library, search, player, scanner, editor. |
| **Whisparr** | Finds new releases of the performers and studios you follow, and sorts downloaded and existing files into your library. |
| **Prowlarr** | Manages the indexers (search sources) that Whisparr uses. Stashbox adds the free public ones for you. |
| **Transmission** | The downloader. |
| **ffmpeg** | Makes thumbnails and previews, and plays videos your browser can't play directly. |

These run quietly in the background. You only ever open **Stashbox**.

## 2. Requirements

| | Windows | Mac |
| --- | --- | --- |
| System | Windows 10 or 11, 64-bit | macOS 12 or later, Apple Silicon (M1 or newer) |
| Also needed | Microsoft Edge or Google Chrome (Edge is built into Windows) | Nothing |
| Disk space | About 2 GB for the programs, plus room for your library | The same |
| Internet | Needed the first time (Whisparr, Prowlarr and the video tools are downloaded then), and for metadata and downloads | The same |

You also need a free **StashDB account** (see [First-time setup](#4-first-time-setup)). A free **TMDB account** is optional and adds movie matching.

## 3. Install

### Windows

1. Run **Stashbox-Setup-1.0.1.exe**.
2. If Windows shows **"Windows protected your PC"**, choose **More info**, then **Run anyway**. (The installer is not signed with a publisher certificate.) No administrator rights are needed; it installs for your Windows account.
3. In the installer you can choose:
   - **Desktop shortcut**: an icon on your Desktop.
   - **Start at login and keep running in the background**: off by default. Turn it on if you want phones and TVs to be able to stream even when the Stashbox window is closed.
4. Leave **Open Stashbox now** ticked and finish.

To open it later, press the **Windows key**, type **Stashbox**, and press Enter. Closing the window quits Stashbox and its background programs (unless you chose to keep it running).

If Windows asks whether to let Stashbox, Whisparr, Prowlarr or Transmission through the firewall, allow **private networks**.

### Mac

1. Open **Stashbox-1.0.1-mac-apple-silicon.dmg** and drag **Stashbox** into **Applications**.
2. Open Stashbox from Applications or Launchpad. The first time, macOS may say it cannot be opened because the developer is unidentified: **right-click the app, choose Open, then Open**. (On newer macOS: System Settings > Privacy & Security > **Open Anyway**.)

Closing the window leaves Stashbox running; click its Dock icon to bring the window back. **Quit Stashbox** (Cmd+Q) quits it and its background programs. To keep it running after you quit, turn on **Stashbox > Keep Running in the Background**.

### The first start

The first time, a progress page shows Stashbox downloading Whisparr, Prowlarr and the video tools. This happens once and takes a few minutes. When it finishes, the app opens by itself.

## 4. First-time setup

A setup page asks for the following. Everything can be changed later in **Settings**.

1. **Username and password.** This is your administrator account. Use at least 10 characters.
2. **StashDB API key (required).** StashDB is the community database Stashbox uses to recognise your videos.
   1. Create a free account at **stashdb.org** and sign in.
   2. Open your **account page** and copy your **API key**.
   3. Paste it into the setup page. Stashbox checks the key before going on.
3. **TMDB API key (optional).** Needed only to match full-length movies. Get a free key from your account settings at **themoviedb.org** (Settings > API).
4. **Media folder (optional).** The folder where your videos already live. Stashbox hands these files to Whisparr, which identifies them and moves them into your library. Files it cannot identify are put in an `unsorted` folder, never deleted.
5. **Library location.** Where Stashbox creates its library. It makes a folder called **Stashbox Library** there, containing:
   - `scenes` and `movies`: the organised library,
   - `unsorted` and `import`: work in progress,
   - `Stashbox Support`: previews, the streaming cache and downloads.

   Choose a drive with **plenty of free space**, such as an external or network drive. If the folder you pick already contains `scenes` or `movies`, Stashbox uses it as it is.

   Use **Choose folder** to browse your computer, or type a path. See also [Network drives](#13-network-drives).

When you click **Create account**, Stashbox starts scanning your library straight away.

> Complete the setup on the computer Stashbox is installed on. The folder browser is only available there until your account exists.

## 5. Finding your way around

The sidebar (or the bar along the bottom on a phone) has:

| Page | What it is for |
| --- | --- |
| **Home** | Continue watching, plus quick ways in (for example your most-watched performers). |
| **Find** | Answer a few questions and Stashbox narrows down what to watch. |
| **Library** | Every clip and movie, with search, sorting and filters. |
| **Performers** | Browse by person. Open one to see everything with them, and to follow them for new releases. |
| **Studios** | Browse by studio. |
| **Saved** | Your queue, favourites, collections and history. |
| **Settings** | All options, plus the tools below. |

**Settings > Library tools** holds the pages you use now and then: **Scanner**, **Editor**, **Add clips**, **Maintenance**, **Tags** and **Guest access**.

Handy shortcuts: press **/** or **Ctrl/Cmd+K** to search from anywhere. Press **G** then **D**, **B**, **Q**, **H** or **M** to jump to Home, Library, Queue, Ready to watch or Maintenance.

## 6. Scanning your library

Open **Settings > Library tools > Scanner** and press **Scan library**. That is all you need to do.

One scan:

- finds new files and adds them,
- matches them with StashDB (and TMDB for movies),
- finishes anything that was left unfinished, such as missing details, performers, thumbnails and previews.

You can leave the page while it works. New files that appear in your folders are also picked up automatically, and you can schedule regular scans in **Settings > Scanner schedule**.

- **Needs attention** (bottom of the Scanner page) lists files Stashbox couldn't process.
- **Export** and **Restore** make and restore a full backup of your library data, watch history and settings.

### What Stashbox does to your files

- **It organises.** Whisparr moves files it has identified from your media folder into the library's `scenes` and `movies` folders, with proper names. Files it can't identify go to `unsorted`.
- **It replaces lower-quality duplicates.** When a newly imported file is the same video as one you already have in lower quality, the lower-quality copy is removed.
- **It does not delete files from inside the app.** Removing a clip in Stashbox removes it from the library but keeps the file on disk. Permanent deletion of files from within Stashbox is switched off.

Keep a backup of anything irreplaceable before you point Stashbox at it.

## 7. Watching

Open any clip or movie to play it. Videos your computer can't play directly are converted on the fly, so every file plays. Stashbox also prepares smoother 480p versions in the background (see [Maintenance](#10-maintenance)); on the Library page you can switch between **480p** and **Original**.

Stashbox remembers where you stopped and offers to **Continue watching** on Home.

### Player controls

The control bar appears when you move the mouse, tap or press a key, and hides after a moment so you can see the whole picture.

| Control | What it does |
| --- | --- |
| Red play button / click the video | Play or pause. |
| Seek bar | Click or drag to jump. Hover to see the time. |
| Back / forward arrows | Skip 10 seconds. |
| Speaker and slider | Mute and volume. |
| **1×** | Playback speed. |
| Picture-in-picture | Keep the video in a small window (where supported). |
| Full-screen button / double-click | Full screen. |

### Keyboard shortcuts

| Key | Action |
| --- | --- |
| **Space** or **K** | Play / pause |
| **Left / Right** | Back / forward 5 seconds |
| **J / L** | Back / forward 10 seconds |
| **Up / Down** | Volume |
| **M** | Mute |
| **F** | Full screen |
| **0 to 9** | Jump to 0% to 90% of the video |

## 8. Getting new content

Stashbox can find and download new releases and sort them into your library for you.

**How it works.** You follow performers or studios. Whisparr searches your indexers for new releases, Transmission downloads them, and Whisparr sorts them into `scenes` and `movies`. Stashbox then scans and shows them. You don't need to touch Whisparr, Prowlarr or Transmission: Stashbox connects them to each other automatically.

1. Open **Settings > Library tools > Add clips**.
2. Search StashDB for a performer or studio and add them. Whisparr will watch for new releases. You can also paste a **magnet link** to download a specific file.
3. Track progress on the same page, from download to automatic sorting.

**Indexers.** Stashbox adds the free public indexers to Prowlarr for you, which can take a few minutes after the first start. For better results you can add your own (private) indexers in Prowlarr. **Settings > Automatic downloads (Downloads section) > Connection check** shows the status of every link in the chain, has an **Open Whisparr** and **Open Prowlarr** link, and a **Fix automatically** button if something is not connected.

Files you already have in your **media folder** are handed to Whisparr the same way.

## 9. Fixing matches, tags and collections

- **Editor** (Settings > Library tools): clips that need a match, least confident first. Pick the right match, or correct the details yourself.
- **Tags**: rename, merge or delete tags. Scene files are never touched.
- **Collections and favourites** are under **Saved**.
- **Guest access**: create time-limited, watch-only links to let someone try Stashbox, or full-access invites for someone who should have the same access as you. Revoke them any time.

## 10. Maintenance

**Settings > Library tools > Maintenance** is for housekeeping, and everything on it also happens automatically:

- **480p streaming preparation**: Stashbox prepares smooth, small versions of your videos in the background so they play well on phones and slower connections. You can watch the progress and retry failed ones here.
- **Repairs**: retry metadata, generate missing artwork, rebuild the search index.
- **Match review, duplicates, file integrity and cleanup.**

## 11. Watching on other devices

Stashbox is available to every device on your home network while it is running.

1. On the computer running Stashbox, find its network address (for example `192.168.1.20`).
2. On your phone, tablet or TV browser, open `http://192.168.1.20:3000` (use your own address).
3. Sign in with your username and password.

On a phone you can use **Share > Add to Home Screen** to make Stashbox look like an app.

Stashbox must be running: keep its window open, or choose **Start at login and keep running in the background** (Windows installer) or **Keep Running in the Background** (Mac menu). Your computer must be awake.

Stashbox is meant for your **home network only**. Do not expose it to the internet.

## 12. Where things are stored

| What | Where |
| --- | --- |
| Program files | **Windows:** `%LOCALAPPDATA%\Stashbox\app` · **Mac:** inside the Stashbox app |
| Database, settings, logs | **Windows:** `%LOCALAPPDATA%\Stashbox` · **Mac:** `~/Library/Application Support/Stashbox` |
| Your library, previews, streaming cache and downloads | The **Stashbox Library** folder you chose in setup |

The database always stays on the computer's own disk. Everything large goes to your library location.

## 13. Network drives

Stashbox runs as you, so any folder you can open on your computer works.

- **Windows:** other drives, mapped network drives (such as `Z:`) and network paths such as `\\nas\videos`. In the folder picker choose a drive, or type the path.
- **Mac:** external drives and network shares that are connected in Finder (they appear under **Drives and network volumes**, or type the path).

Connect the drive before starting Stashbox. If the drive is not connected when Stashbox starts, it can't reach your library until it is.

## 14. Backup, update and uninstall

**Backup.** Scanner > **Export** saves your library data, watch history and settings in one file. **Restore** brings it back. Your video files are not part of the backup.

**Update.** Install the newer version over the old one (run the new installer, or drag the new app into Applications). Your library and settings are kept.

**Uninstall.**
- **Windows:** Settings > Apps > Installed apps > **Stashbox** > Uninstall. It asks whether to delete the database and settings too. Your own videos are never deleted.
- **Mac:** quit Stashbox and drag it to the Trash. To remove its data as well, delete `~/Library/Application Support/Stashbox`.

## 15. Troubleshooting

**Windows says "Windows protected your PC" / Mac says the app can't be opened.**
The installer isn't signed with a publisher certificate. Windows: **More info > Run anyway**. Mac: right-click the app, **Open**, then **Open** (or System Settings > Privacy & Security > **Open Anyway**).

**The first start is slow.**
Stashbox is downloading Whisparr, Prowlarr and the video tools. The progress page shows each download. If one fails, it retries by itself every few minutes, or press **Try again**.

**The page is white or unstyled, or "Something went wrong" appears.**
Quit Stashbox completely and open it again. If it still happens, the error screen has a **Details** section with a **Copy details** button, and a **Clear cache and reload** button. Send the details to whoever supports you.

**Nothing shows up after scanning.**
Check that your videos are in your **media folder** or your library's `scenes` or `movies` folder, and that the files end in a common video extension (mp4, mkv, mov, webm). Then press **Scan library** again. Open **Needs attention** on the Scanner page for files that couldn't be processed.

**New downloads don't happen.**
Open **Settings > Downloads > Connection check**. Red items say what is missing; **Fix automatically** repairs most of them. If **Indexers** is red, wait a few minutes after the first start, or add an indexer in Prowlarr.

**Another program already uses a port.**
Stashbox needs a few network ports (3000, 8080, 9091, 6969 and 9696 by default). If one is taken, it picks a free one automatically. **Open Whisparr** and **Open Prowlarr** in the Connection check always show the right addresses.

**A video won't play, or plays slowly.**
Stashbox converts incompatible videos on the fly, which needs some processing power. Choose **480p** on the Library page player for a lighter stream, and let **Maintenance > 480p streaming preparation** finish.

**Diagnostics and logs.**
- **Mac:** **Stashbox > Diagnostics** (Cmd+Option+D) shows what each background program is doing and lets you copy a report. **Stashbox > Show Logs in Finder** opens the log folder.
- **Windows:** open `http://127.0.0.1:3900/diagnostics` in a browser on the same computer. Logs are in `%LOCALAPPDATA%\Stashbox\logs`.
- **Settings > Health** shows library and service health on both.

**Stop everything.**
Windows: Start menu > **Stop Stashbox**. Mac: quit Stashbox.

## 16. Privacy and security

- Your library, watch history and settings stay on your computer. Stashbox has no account system and sends no analytics.
- Stashbox contacts the **services it needs to do its job**: StashDB and TMDB to recognise your videos, the sites it downloads Whisparr, Prowlarr and ffmpeg from on first start, and the indexers and torrent network when you download.
- Torrent downloads are visible to the people you share them with. If that matters to you, use a VPN. Stashbox does not provide one.
- The control pages of Whisparr, Prowlarr and Transmission only listen on your own computer (Transmission also uses one port for torrent traffic). Stashbox itself listens on your home network (port 3000) and always asks for your password.
- Keep your password private and use **Guest access** for anyone else. Do not expose Stashbox to the internet.

## 17. Responsible use

Stashbox is software for organising your own media library. It contains adult-oriented metadata sources and is intended for **adults aged 18 or over**. You are responsible for the content you store and download and for following the laws that apply to you, including copyright. Only download material you have the right to have.

## 18. Included software and licences

Stashbox installs and runs these separate programs. They are not part of Stashbox and are used under their own licences. Source code for each is available from the links below.

| Program | Licence | Source |
| --- | --- | --- |
| Whisparr | GPL-3.0 | github.com/Whisparr/Whisparr-Eros |
| Prowlarr | GPL-3.0 | github.com/Prowlarr/Prowlarr |
| Transmission | GPL-2.0-or-later / GPL-3.0 | transmissionbt.com |
| FFmpeg | LGPL / GPL (depending on the build) | ffmpeg.org |
| Node.js | MIT | nodejs.org |

The full list, including the libraries these use, is in **THIRD-PARTY-NOTICES.txt**.

---

*Stashbox 1.0.1 · November 2026*
