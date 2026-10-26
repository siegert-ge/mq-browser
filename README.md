# MQ Browser – read any IBM MQ queue, browse-only

**MQ Browser** is a Windows desktop tool for developers, testers and operations teams working with
IBM MQ. It reads queues **strictly by browsing** – messages are never consumed, changed or put – and
shows every message decoded and readable. Search several queues of several queue managers at once
by time range and text, and stay fast on queues with 100,000+ messages.

> **Free trial:** all features for 14 days, then *MQ Browser Lite* (max. 10 messages per browse,
> no export) – free, no registration. **[Download the trial](../../releases/latest)** ·
> **[Buy the full version](https://shop.siegert.ge/#products)** (Single User € 59 / $ 69 · Team € 199 / $ 229)

<!-- Add a real screenshot: docs/images/main-window.png -->
![MQ Browser main window](docs/images/main-window.png)

## Why MQ Browser

| | MQ Browser | MQ Explorer | RFHUtil | MO71 |
|---|---|---|---|---|
| Reads messages | **browse only** | browse | browse **and destructive get** | browse **and destructive get** |
| Can delete / clear / put | **no – technically impossible** | yes | yes | yes |
| Several queues & queue managers in one result list | **yes, time-sorted** | no | no | no |
| Time-range filter and full-text search | **yes** | no | no | no |
| Decodes RFH2, embedded Hex/Base64, DLQ, XMIT, PCF | **yes** | partly | partly | partly |
| Fixed-length / EBCDIC / packed-decimal records | **yes, with layouts** | no | no | no |

More: [MQ Browser vs. MQ Explorer, RFHUtil, MO71](https://shop.siegert.ge/compare-mq-tools.html)

## Features

- **Browse only** – queues are opened with `MQOO_BROWSE | MQOO_INQUIRE` only; no `MQOO_INPUT`/`MQOO_OUTPUT`.
- **Many queues at once** – environments, queue managers, queue filters and saved *routes*; one time-sorted hit list.
- **Readable output** – all MQMD fields, RFH2 folders, pretty-printed XML/SOAP/JSON in the style of Logstash `rubydebug`.
- **Embedded content** – Hex and Base64 inside XML expanded recursively, including binary MQMDs; long binaries (PDFs) shortened.
- **System messages** – dead-letter header (MQDLH), transmission header (MQXQH), PCF events and commands.
- **Records** – fixed-length and delimited records with named fields; EBCDIC, zoned and packed decimals.
- **Deep queues** – header mode and early stop read 100,000+ messages in seconds.
- **Search & export** – AND, phrases, exclusions, regex; histogram; export to text.

## Requirements

- Windows, Java 17 or newer (JRE is enough)
- IBM MQ client Java libraries (`com.ibm.mq.allclient.jar`) – not included
- Network access to your queue managers; MQ authorities `+connect +inq` and `+browse +inq`

## Quick start

1. Download `mq-browser-trial.zip` from **[Releases](../../releases/latest)** and unzip it.
2. Enter your queue managers in `config\mq-browser.json` – see [examples](examples/).
3. Run `start.cmd` (or `start.cmd debug` to see error output).

Full documentation: the user manual (PDF) is included in the download –
[preview](https://shop.siegert.ge/assets/documents/preview-mq-browser.pdf).

## Guides

- [How to read a dead-letter queue without removing messages](https://shop.siegert.ge/read-ibm-mq-dead-letter-queue.html)
- [How to search deep IBM MQ log queues by time and text](https://shop.siegert.ge/search-deep-ibm-mq-queues.html)

## Questions, bugs, ideas

Please open an **[issue](../../issues/new/choose)**. For license and order questions:
info@siegert.ge.

## License

MQ Browser is **commercial software, not open source**. This repository contains documentation,
examples and the trial download – no source code. The trial is governed by
[TRIAL-TERMS.txt](TRIAL-TERMS.txt), the full version by the
[EULA](https://shop.siegert.ge/eula-mq-browser.html).

© 2026 I/E Marc Siegert, Tbilisi, Georgia · https://shop.siegert.ge

IBM and IBM MQ are trademarks of International Business Machines Corporation. MQ Browser is not
affiliated with or endorsed by IBM.
