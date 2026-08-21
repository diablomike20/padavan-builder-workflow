# [Padavan ng CAKE Linux 3.4 Builder

## 🚀 Supported Devices (Kernel 3.4)

We support a massive array of **MT7620/MT7621** devices. Pick the one you love!
*(This list corresponds directly to the `target_select` menu in the build workflow.)*

| Brand | Supported Models |
| :--- | :--- |
| **TP-Link** | **Archer C2 (V1)**, C20 (V1/V4/V5), C5 (V4), C50 (V1/V3/V4), EC220-G5 (V2), MR200 (V1), MR3020 (V3), MR3420 (V5), WDR7300 (V5), WR840N (V4/V5/V6/RU), WR841N (V13/V14), WR842N (V5), WR845N (V3/V4) |
| **Xiaomi** | MI-3, MI-3C, MI-4 (A/C/SPI), MI-4A (100M), MI-MINI, MI-NANO, MI-R3G (v1/v2/SPI), MI-R3P (Pro), R2100 (AC2100), RM-AC2100 |
| **ASUS** | RT-AC1200 (GU/HP), RT-AC51U, RT-AC54U, RT-N10+, RT-N11P (B1), RT-N12+, RT-N13U (B1), RT-N14U, **RT-N56U (A1/B1/GE2)**, RP-AC56 |
| **ZyXEL** | Keenetic Series: **Giga III**, **Ultra II**, Extra (I/II), Lite (I/II/III/3B), Omni (I/II), Start II, Viva, 4G III (B) |
| **D-Link** | DIR-300 (B1/B7), DIR-320 (B1), DIR-620 (A1/D1), DIR-860L, **DIR-882** |
| **Newifi** | Newifi D1, Newifi D2, Newifi Mini, Newifi Y1S |
| **GL.iNet** | GL-MT300A, GL-MT300N (V1/V2) |
| **Phicomm** | K2P (PSG1218), 256PSG1218 |
| **ZBT** | WE1326, WE1626, WE826-T2, WG3526 (-32), WR8305RT |
| **Others** | **Ubiquiti** ER-X, **Linksys** EA-8100, **Belkin** F9K1103, **Totolink** A3004NS, **HiWiFi** HC5661A, **Youku** L1/L1C, **ZTE** E8820S |
| **OEM/Misc** | 5K-W20, A5-V11, ALR-U270, MQ-WITI, Nexx WT3020 (A/H), Samsung SWR1100, Sercomm (S1010/SmartBox), SNR (MD1/ME1/W4N), Tuoshi TS7620N, Unielec U7621, Wall-AP, Youhua WR1200JS |

---

## 🌐 Multi-Language Support

We believe in a borderless internet. The firmware now supports **14 Languages** out of the box!
*(Select your preferred language in the `language_select` menu.)*

* **English_Only** (Default)
* **CN (繁體中文)** - Traditional Chinese
* **RU (Pусский)** - Russian
* **ES (Español)** - Spanish
* **BR (Brazil)** - Portuguese
* **CZ (Česky)** - Czech
* **DA (Dansk)** - Danish
* **DE (Deutsch)** - German
* **FI (Finsk)** - Finnish
* **FR (Français)** - French
* **NO (Norsk)** - Norwegian
* **PL (Polski)** - Polish
* **SV (Svensk)** - Swedish
* **UK (Українська)** - Ukrainian

---

## 🛠️ Usage (How to Build)

This workflow uses **GitHub Actions** to build firmware in the cloud. You don't need a Linux PC!

### 1. Start the Workflow
1.  Go to the **[Actions](../../actions)** tab in this repository.
2.  Select the workflow **"Build firmware (Ultimate Fix)"** (or `build.yml`) from the left sidebar.
3.  Click the **Run workflow** button on the right.

### 2. Configure Your Build (Interactive Inputs)
You will see a menu with the following options. **Customize it to your liking!**

* **target_select** (Required):
    * Choose your router model from the list (e.g., `TL_C2-V1`, `MI-MINI`, `RT-N56U`, `K2P`...).
    * *Note: This list includes all supported 3.4 kernel devices.*

* **language_select** (New!):
    * `English_Only`: Keeps the interface clean and lightweight.
    * `CN (繁體中文)` / `RU` / `ES` etc.: Automatically adds your selected language pack.

* **nanoversion**:
    * `true`: Performs extreme size optimization (removes unused modules) to fit into small flash memory (4MB/8MB).

* **customization**:
    * Set your default WiFi SSID, Password, and Login credentials here (JSON format).

### 3. Wait & Download
1.  Click the green **Run workflow** button.
2.  The build process usually takes **15 to 40 minutes**.
3.  When the circle turns **Green (Success)**, click on the task.
4.  Scroll down to the **Artifacts** section to download your firmware `.zip` file.

---

## ⚖️ Credits & Disclaimer

This project is based on `shvchk/padavan-builder-workflow` and the incredible `padavan-ng` project by **Sergey Hadzhioglu**.

### Support the Original Developers
To express gratitude and support Sergey's work on Padavan-NG:
* **ЮMoney wallet**: `4100118647832050`
* [Link for quick replenishment](https://yoomoney.ru/to/4100118647832050)

### DISCLAIMER
**NO WARRANTY OR SUPPORT**
This product includes copyrighted third-party software. The firmware is provided "AS IS" without warranty of any kind. You expressly acknowledge that use of this software is at your sole risk. Flash at your own risk!

---

<p align="right">English | <a href="README.ru.md">Русский</a></p>

## Automatic Padavan firmware builds using GitHub servers

### Usage

- [Fork this repository](https://github.com/shvchk/padavan-builder-workflow/fork), further steps should be performed in your fork

- Copy your build config to [`build.config`](build.config)

  Build config template can be found in the [firmware repository](https://gitlab.com/hadzhioglu/padavan-ng/-/tree/master/trunk/configs/templates)

- Run the build process: [Actions](../../actions) → [Build firmware](../../actions/workflows/build.yml) → Run workflow

  ![run workflow](misc/run-workflow.webp)

  The build process will appear on the same page (if it doesn't appear, just refresh the page). You can get process details by clicking on it.

  Depending on the build config, build process usually takes from 10 to 60 minutes.

- While the process is in progress, its status indicator would be gold-ish circle

  ![workflow status progress](misc/workflow-status-in-progress.webp)

- If the process finishes successfully, its status indicator would turn green with a check mark

  ![workflow status success](misc/workflow-status-success.webp)

  Click on the finished process. Archive with the firmware would be stored as its artifact:

  ![workflow artifacts](misc/workflow-artifacts.webp)

  Firmware license does not permit binaries distribution, so artifacts are stored for 7 days for personal use.

- If the process finishes with an error, its status indicator would turn red with a cross

  ![workflow status fail](misc/workflow-status-fail.webp)

  Click on the finished process. To get details about the error, click on the failed `build` job at the left:

  ![workflow details fail](misc/workflow-details-fail.webp)

  Job report will be opened:

  ![workflow details get logs](misc/workflow-details-get-logs.webp)

  Here it's immediately obvious that it was *Check firmware size* step that failed — it is marked with a red circle with a cross. Specific reason is shown below: *Firmware size (18,492,849 bytes) exceeds max size (16,187,392 bytes) for your target device* — i.e. built firmware size is too big for the target device.

  In case of any error its reason is usually shown at the end of the log, as in the example above. To view full log click on the cog ⚙️ icon in the top right corner → View raw logs. You can also download compressed log archive in the same menu → Download log archive.

  If you can't figure out the problem on your own, you can ask community or firmware developer for help. In this case don't forget to attach the log archive.


### Updating your fork

To sync your fork with its origin repository, just click *Sync fork* → *Update branch* at the top of the main page of your fork:

![sync fork](misc/sync-fork.webp)


### Advanced usage

You can set the firmware repository, branch, specific tag or commit in the [`variables`](variables) file.

In the [`variables`](variables) file you can also specify which themes you want to install by uncommenting theme names in the `PADAVAN_THEMES` variable. Themes repository can be set with the `PADAVAN_THEMES_REPO` variable.

You can create a `pre-build.sh` script with any custom commands, which will be executed just before build process. By that time firmware source code is already downloaded, so you can add or change anything in it.

You can create a `post-build.sh` script, which will be executed right after build process.


---

Discussion: https://github.com/shvchk/padavan-builder-workflow/discussions/categories/general
