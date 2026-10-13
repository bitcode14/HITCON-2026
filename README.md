# HITCON 2026 x DEVCORE Wargame
https://devco.re/blog/2026/10/08/vendor-as-attack-surface-2026-hitcon-wargame/
This repository is an archive of HITCON 2026 x DEVCORE Wargame.

## Description

今年的主軸是「把套件裝在網站根目錄下」可能帶來的風險：平台會依你選定的 `{PHP Version, Composer Package, Package Version}` 準備對應的 challenge container，題目的 web root 固定是 `/var/www/html`，Composer 會把套件安裝在這裡（通常在 `/var/www/html/vendor`）。參賽者針對任一題目組合提交一支 exploit script，由平台在獨立 container 中執行、尋找輸出中的 flag。

This year's theme demonstrates the risk of installing a package directly under the web root: the platform prepares a challenge container matching your chosen `{PHP Version, Composer Package, Package Version}` tuple. The challenge web root is always `/var/www/html`, and Composer installs the package there (usually under `/var/www/html/vendor`). Participants submit one exploit script per challenge; the platform runs it in an isolated container and looks for a flag in its output.

## Scoreboard

* [scoreboard.md](https://github.com/DEVCORE-Wargame/HITCON-2026/tree/main/scoreboard.md) — 最終排名 (final ranking)
* [matrix.md](https://github.com/DEVCORE-Wargame/HITCON-2026/tree/main/matrix.md) — 每位參賽者在每個 package 的 AC / PA 結果 (per-participant AC/PA result for every package)

## Challenges

每個 package 的滿分就是它的星星數（stars）；`AC` 得到 100% 分數，`PA`（讀到 `/flag1`）得到 `floor(stars / 2)`。同一個 package 在不同 PHP 版本下分開計分。完整規則與 verdict 說明請見下方「Page Backup」。

Each package's maximum score is its star count; `AC` awards 100% of that score, `PA` (reading `/flag1`) awards `floor(stars / 2)`. The same package on different PHP versions is scored separately. See "Page Backup" below for the full rules and verdict reference.

### Scored packages

以下僅列出在 [scoreboard.md](https://github.com/DEVCORE-Wargame/HITCON-2026/tree/main/scoreboard.md) / [matrix.md](https://github.com/DEVCORE-Wargame/HITCON-2026/tree/main/matrix.md) 上至少有一筆 `AC` / `PA` 記錄的 package（題目組合），**並非比賽開放的完整套件清單**。

The list below only covers packages (challenge tuples) that received at least one `AC` / `PA` result on [scoreboard.md](https://github.com/DEVCORE-Wargame/HITCON-2026/tree/main/scoreboard.md) / [matrix.md](https://github.com/DEVCORE-Wargame/HITCON-2026/tree/main/matrix.md); **it is not the full set of packages offered in the event**.

* [`api-platform/api-pack`](https://packagist.org/packages/api-platform/api-pack) — 1.4.0 (PHP 8.4)
* [`brianium/paratest`](https://packagist.org/packages/brianium/paratest) — 6.11.1 (PHP 7.4.33), 7.23.1 (PHP 8.4)
* [`codeception/codeception`](https://packagist.org/packages/codeception/codeception) — 4.2.2 (PHP 7.4.33), 5.3.5 (PHP 8.4)
* [`creolab/laravel-modules`](https://packagist.org/packages/creolab/laravel-modules) — 0.5.6 (PHP 7.4.33), 0.5.6 (PHP 8.4)
* [`css-crush/css-crush`](https://packagist.org/packages/css-crush/css-crush) — 4.2.0 (PHP 7.4.33)
* [`datadog/dd-trace`](https://packagist.org/packages/datadog/dd-trace) — 1.23.3 (PHP 7.4.33), 1.23.3 (PHP 8.4)
* [`dg/ftp-deployment`](https://packagist.org/packages/dg/ftp-deployment) — 3.5.2 (PHP 7.4.33), 3.7.0 (PHP 8.4)
* [`doctrine/doctrine-migrations-bundle`](https://packagist.org/packages/doctrine/doctrine-migrations-bundle) — 3.7.0 (PHP 7.4.33), 4.0.0 (PHP 8.4)
* [`doctrine/migrations`](https://packagist.org/packages/doctrine/migrations) — 3.5.5 (PHP 7.4.33), 3.9.7 (PHP 8.4)
* [`dominicsayers/isemail`](https://packagist.org/packages/dominicsayers/isemail) — 3.0.7 (PHP 7.4.33), 3.0.7 (PHP 8.4)
* [`driftingly/rector-laravel`](https://packagist.org/packages/driftingly/rector-laravel) — 2.5.0 (PHP 7.4.33), 2.5.0 (PHP 8.4)
* [`friendsofsymfony1/symfony1`](https://packagist.org/packages/friendsofsymfony1/symfony1) — 1.5.24 (PHP 7.4.33)
* [`humbug/humbug`](https://packagist.org/packages/humbug/humbug) — 1.0.0-alpha2 (PHP 8.4)
* [`internations/http-mock`](https://packagist.org/packages/internations/http-mock) — 0.14.0 (PHP 7.4.33), 0.12.0 (PHP 8.4)
* [`jakub-onderka/php-parallel-lint`](https://packagist.org/packages/jakub-onderka/php-parallel-lint) — 1.0.0 (PHP 7.4.33)
* [`jmose/command-scheduler-bundle`](https://packagist.org/packages/jmose/command-scheduler-bundle) — 1.2.7 (PHP 8.4)
* [`lexik/translation-bundle`](https://packagist.org/packages/lexik/translation-bundle) — 8.1.0 (PHP 8.4)
* [`lexpress/symfony1`](https://packagist.org/packages/lexpress/symfony1) — 1.5.24 (PHP 7.4.33)
* [`luracast/restler`](https://packagist.org/packages/luracast/restler) — 5.0.15 (PHP 7.4.33)
* [`magento/magento-coding-standard`](https://packagist.org/packages/magento/magento-coding-standard) — 31 (PHP 7.4.33), 40 (PHP 8.4)
* [`mamuz/php-dependency-analysis`](https://packagist.org/packages/mamuz/php-dependency-analysis) — 2.0.2 (PHP 7.4.33)
* [`nette/tester`](https://packagist.org/packages/nette/tester) — 2.4.3 (PHP 7.4.33), 2.6.1 (PHP 8.4)
* [`oddvalue/laravel-drafts`](https://packagist.org/packages/oddvalue/laravel-drafts) — 3.2.0 (PHP 8.4)
* [`owasp/phprbac`](https://packagist.org/packages/owasp/phprbac) — 2.0.0 (PHP 7.4.33), 2.0.0 (PHP 8.4)
* [`pestphp/pest`](https://packagist.org/packages/pestphp/pest) — 5.0.2 (PHP 8.4)
* [`phing/phing`](https://packagist.org/packages/phing/phing) — 2.17.4 (PHP 7.4.33)
* [`phpbench/phpbench`](https://packagist.org/packages/phpbench/phpbench) — 1.2.14 (PHP 7.4.33), 1.7.0 (PHP 8.4)
* [`phpwhois/phpwhois`](https://packagist.org/packages/phpwhois/phpwhois) — 4.2.5 (PHP 7.4.33)
* [`pingplusplus/pingpp-php`](https://packagist.org/packages/pingplusplus/pingpp-php) — 2.6.0 (PHP 7.4.33), 3.0.0 (PHP 8.4)
* [`potsky/pimp-my-log`](https://packagist.org/packages/potsky/pimp-my-log) — 1.7.10 (PHP 7.4.33)
* [`propel/propel`](https://packagist.org/packages/propel/propel) — 2.0.0-beta4 (PHP 7.4.33), 2.0.0 (PHP 8.4)
* [`propel/propel1`](https://packagist.org/packages/propel/propel1) — 1.7.2 (PHP 7.4.33), 1.7.2 (PHP 8.4)
* [`ptrofimov/beanstalk_console`](https://packagist.org/packages/ptrofimov/beanstalk_console) — 1.9.2 (PHP 7.4.33), 1.9.2 (PHP 8.4)
* [`rector/rector`](https://packagist.org/packages/rector/rector) — 2.5.9 (PHP 7.4.33)
* [`rector/rector-laravel`](https://packagist.org/packages/rector/rector-laravel) — 2.5.0 (PHP 7.4.33), 2.5.0 (PHP 8.4)
* [`roave/no-leaks`](https://packagist.org/packages/roave/no-leaks) — 1.3.0 (PHP 7.4.33), 1.3.0 (PHP 8.4)
* [`sami/sami`](https://packagist.org/packages/sami/sami) — 4.1.2 (PHP 7.4.33)
* [`schickling/backup`](https://packagist.org/packages/schickling/backup) — 0.6.0 (PHP 7.4.33), 0.6.0 (PHP 8.4)
* [`shardj/zf1-future`](https://packagist.org/packages/shardj/zf1-future) — 1.25.0 (PHP 7.4.33), 1.25.0 (PHP 8.4)
* [`sjparkinson/static-review`](https://packagist.org/packages/sjparkinson/static-review) — 5.2.2 (PHP 7.4.33), 5.1.3 (PHP 8.4)
* [`sulu/sulu`](https://packagist.org/packages/sulu/sulu) — 3.0.8 (PHP 8.4)
* [`symfony/framework-standard-edition`](https://packagist.org/packages/symfony/framework-standard-edition) — 3.4.47 (PHP 7.4.33), 3.4.47 (PHP 8.4)
* [`symfony/orm-pack`](https://packagist.org/packages/symfony/orm-pack) — 2.7.0 (PHP 8.4)
* [`symfony/symfony`](https://packagist.org/packages/symfony/symfony) — 5.4.53 (PHP 7.4.33), 6.3.12 (PHP 8.4)
* [`symfony/symfony-demo`](https://packagist.org/packages/symfony/symfony-demo) — 1.6.1 (PHP 7.4.33)
* [`symplify/easy-coding-standard`](https://packagist.org/packages/symplify/easy-coding-standard) — 13.2.17 (PHP 7.4.33), 13.2.17 (PHP 8.4)
* [`symplify/monorepo-builder`](https://packagist.org/packages/symplify/monorepo-builder) — 12.7.2 (PHP 8.4)
* [`verot/class.upload.php`](https://packagist.org/packages/verot/class.upload.php) — 2.1.6 (PHP 7.4.33), 2.1.6 (PHP 8.4)
* [`vrana/adminer`](https://packagist.org/packages/vrana/adminer) — 5.5.1 (PHP 7.4.33), 5.5.1 (PHP 8.4)
* [`yurunsoft/pay-sdk`](https://packagist.org/packages/yurunsoft/pay-sdk) — 3.1.8 (PHP 7.4.33), 3.1.8 (PHP 8.4)
* [`zendframework/skeleton-application`](https://packagist.org/packages/zendframework/skeleton-application) — 2.5.0 (PHP 8.4)
* [`zendframework/zendframework`](https://packagist.org/packages/zendframework/zendframework) — 2.5.2 (PHP 8.4)
* [`zendframework/zendframework1`](https://packagist.org/packages/zendframework/zendframework1) — 1.12.20 (PHP 7.4.33)

## Page Backup

### INFO

* 比賽時間：即日起 - 2026/8/22 (六) 14:00
* 比賽方式：平台會為你選定的 package / version / PHP version 準備對應的 challenge container。每組 `{PHP Version, Composer Package, Package Version}` 都是一個題目，可以選擇任意題目提交一支 exploit script；成功讀到 `/flag1` 為部分成功（PA），成功執行 `/readflag` 為完整解出（AC）。
* 領獎時間：2026/8/22 (六) 14:30 - 15:00（下午茶時間）
* 領獎辦法：
    * 請於領獎時間內至 DEVCORE 展攤（4 樓 P1，近 R0 後門），將後台解題頁面顯示給工作人員，核對身分無誤後即可獲得對應名次之贈品。
    * 未至現場領取視同放棄。
    * 15:00 後開放有得分的參賽者領取未發完的紀念品，先到先贏，發完為止。
* 問題回報：如果顯示 JE，代表平台端有問題，請到聊天室詢問。

### INFO (English)

* Game time: now through Saturday, August 22, 2026, 14:00
* Format: The platform prepares a matching challenge container for the package / version / PHP version you select. Every `{PHP Version, Composer Package, Package Version}` tuple is a challenge; you may choose any challenge and submit one exploit script. Reading `/flag1` is a partial success (PA); executing `/readflag` is a full solve (AC).
* Award Collection time: Saturday, August 22, 2026, 14:30-15:00 (afternoon tea break)
* Award Collection Procedure:
    * Visit the DEVCORE booth (4F P1, near the R0 back entrance) during the prize claim period and show the staff your solved-challenges page in the admin area. After your identity is verified, you will receive the prize for your final rank.
    * If you do not claim your prize on site, it will be treated as forfeited.
    * After 15:00, participants with a positive score may claim any remaining souvenirs on a first-come, first-served basis until they run out.
* Problem Reporting: If you see JE, the platform side failed; contact the admins in the chat room.

### AWARD

* 🥇🥈 第 1 - 2 名：GL.iNet GL-BE3600 (Slate 7)
* 🥉 第 3 名：M5Stack Cardputer ADV Hacker Kit
* 第 4 - 20 名：限定 DEVCORE 啤酒組（單支／口味隨機出貨）

根據相關法規，禁止提供酒精飲料給未成年者。會眾領獎時，敬請出示有顯示出生年月日的任一身分證件（如健保卡、身分證等）。解題者若在活動當日未滿 18 歲（生日晚於 2008 年 8 月 21 日），將贈送等值的其他獎品代替。

### AWARD (English)

* 🥇🥈 1st-2nd place: GL.iNet GL-BE3600 (Slate 7)
* 🥉 3rd place: M5Stack Cardputer ADV Hacker Kit
* 4th-20th place: Limited DEVCORE Beer Set (single bottle, flavor shipped at random)

By applicable regulations, alcoholic beverages cannot be provided to minors. Please show an identity document with your date of birth when claiming the prize on site. If a solver is under 18 years old on the event date (born after August 21, 2008), an alternative prize of equivalent value will be provided instead.

### NOTES

* 請只針對題目環境與平台開放的 package 作答。
* 不要把流量送到不在題目範圍內的外部系統。
* Packages 頁面會顯示每一題的下載數、星數、被嘗試次數與成功次數。
* 本次 Wargame 情境主軸是呈現將套件安裝在網站根目錄下可能產生的問題，而非尋找套件的 0day。因此 DEVCORE 不會將本次 Wargame 中由參賽者發現的 Exploit 當作 0day 進行回報，如果參賽者認為該 Exploit 是該套件的 0day，可逕行回報，無須通知 DEVCORE。
* 承上，為保護可能於 Wargame 過程中發現的 0day，本次 Wargame 過程中只會揭露星星數少於 500 且下載次數少於 1,000,000 次的套件的成功解題次數，其餘套件的解題次數將於 Wargame 結束後再擇期公開。

### NOTES (English)

* Please only attack the provided challenge environment and packages exposed by the platform.
* Do not send traffic to unrelated external systems.
* The Packages page shows downloads, stars, attempt counts, and success counts for each challenge.
* This Wargame is designed to demonstrate the risks of installing packages directly under the web root, not to encourage participants to hunt for package 0-days. DEVCORE will not report exploits discovered during this Wargame as 0-days. If you believe your exploit is a genuine 0-day in the package itself, you may report it directly without notifying DEVCORE.
* To reduce the risk of exposing 0-days discovered during the event, successful solve counts will be shown during the Wargame only for packages with fewer than 500 stars and fewer than 1,000,000 downloads. Solve counts for all other packages will be disclosed later after the Wargame ends.

### SCORING RULES

* 每個 package 的滿分就是它的星星數（stars）。
* `AC` 得到該 package 的 100% 分數，也就是 `stars`。
* `PA` 得到該 package 的 50% 分數，採整數下取整，也就是 `floor(stars / 2)`。
* 排行榜以各 package 的最佳有效結果計分。
* 同一個 package 在不同 PHP 版本下分開計分。
* 同一題如果你之後交出更好的結果，排行榜會以更好的那次為準。
* 完整解出越多 package、且解出高星數 package，總分就越高。
* 同分者以最早達到該分數為較高的排名。

### SCORING RULES (English)

* The maximum score for a package is its star count on the platform.
* `AC` awards 100% of that package score, i.e. `stars`.
* `PA` awards 50% of that package score using integer floor, i.e. `floor(stars / 2)`.
* The scoreboard uses your best valid result for each package.
* The same package on different PHP versions is scored separately.
* If you later submit a better result for the same challenge, the better one replaces the older one on the scoreboard.
* Solving more packages and solving higher-star packages yields a higher total score.
* Ties are broken by who reached that score earlier.

### EXPLOIT SCRIPT

* 你提交的 exploit 會在獨立的 container 中啟動，並以 challenge container 的 Hostname 作為參數傳入。
* Exploit container 的 entrypoint 會在 challenge container 成功啟動後，用 `/exploit <host>` 執行你的腳本。
* 你的程式應該自己連線、送請求、完成利用，最後正常結束。
* Judge 會在 exploit stdout 內容中尋找 flag，若有找到，就視為挑戰成功。
* 你要把 exploit 寫成「可直接執行」的腳本，例如 Shell / Python 腳本。

```python
#!/usr/bin/env python3
import sys
import requests

challenge = sys.argv[1]
response = requests.get(f"http://{challenge}", timeout=5)
print(response.text)
```

### EXPLOIT SCRIPT (English)

* Your exploit runs in a separate container and receives the challenge container hostname as its argument.
* After the challenge container starts successfully, the exploit container entrypoint runs your script as `/exploit <host>`.
* Your script should connect to the target, send requests, complete the exploit, and exit normally.
* The judge looks for flags in exploit stdout. If a flag appears, the attempt is treated as successful.
* You should write the exploit as a directly executable script, for example a shell or Python script.

### RUNTIME LIMITS

* 你的 exploit 會在獨立容器中執行，第一個參數是 challenge host。
* 目前提供兩種 challenge PHP 版本：`7.4.33` 與 `8.4`。
* 執行時間限制是 60 秒，超過會得到 `TLE`。
* exploit 記憶體限制是 128 MiB，超過會得到 `MLE`。
* challenge 服務本身的記憶體限制是 256 MiB。
* CPU 配額約為 0.5 core。
* exploit 容器的 Process 數上限是 64；challenge 容器的 Process 數上限是 128。
* 容器會使用隔離的內部網路，無法對外連線。
* exploit 只有 `/tmp` 可寫。

### RUNTIME LIMITS (English)

* Your exploit runs in a separate container and receives the challenge host as its first argument.
* Two challenge PHP versions are currently available: `7.4.33` and `8.4`.
* The time limit is 60 seconds. Exceeding it results in `TLE`.
* The exploit memory limit is 128 MiB. Exceeding it results in `MLE`.
* The challenge service itself is limited to 256 MiB of memory.
* CPU quota is roughly 0.5 core.
* The exploit container is limited to 64 processes, and the challenge container is limited to 128.
* Containers use an isolated internal network and cannot reach the public Internet.
* Inside the exploit container, only `/tmp` is writable.

### VERDICTS

| Verdict | 說明 | Description |
| --- | --- | --- |
| AC / Accepted | 成功執行 `/readflag`。這是完整解題。 | Execute `/readflag`. This is a full solve. |
| PA / Partial Accepted | 成功讀到 `/flag1`，但還沒有完成最終目標。 | Read `/flag1` without completing the final objective. |
| WA / Wrong Answer | 程式有跑完，但沒有達成目標。 | Your script finished running but did not reach the goal. |
| TLE / Time Limit Exceed | 程式執行超時。 | Your script exceeded the time limit. |
| MLE / Memory Limit Exceed | 程式超過記憶體限制。 | Your script exceeded the memory limit. |
| RE / Runtime Error | 你的 exploit 本身執行失敗。 | Your exploit itself crashed or failed to run correctly. |
| JE / Judge Error | 平台環境或基礎設施異常，這不代表你的 exploit 成功或失敗，請聯繫管理員。 | The platform or infrastructure failed. This does not mean your exploit was correct or incorrect; contact the admins. |
