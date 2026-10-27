# com.etendoerp.metadata.template

[![Release](https://img.shields.io/github/v/release/etendosoftware/com.etendoerp.metadata.template?label=release)](https://github.com/etendosoftware/com.etendoerp.metadata.template/releases)  
[![Build](https://img.shields.io/github/actions/workflow/status/etendosoftware/com.etendoerp.metadata.template/gradle.yml?label=build)](https://github.com/etendosoftware/com.etendoerp.metadata.template/actions)  
[![License](https://img.shields.io/github/license/etendosoftware/com.etendoerp.metadata.template)](https://github.com/etendosoftware/com.etendoerp.metadata.template/blob/develop/LICENSE)

---

This module is part of the **EtendoERP** ecosystem and acts as the template module for [com.etendoerp.metadata](https://github.com/etendosoftware/com.etendoerp.metadata).

This module is **required** to run the new Etendo UI:  
👉 [com.etendoerp.mainui](https://github.com/etendosoftware/com.etendoerp.mainui)

---

## Exporting process JavaScript

The process scripts of the new UI (`EM_ETMETA_*` columns of `OBUIAPP_PROCESS` and `OBUIAPP_PARAMETER`) are
delivered by this module as configuration script changes (`src-db/database/configScript.xml`).

To export a change:

1. Install this module from source and set it **In Development**.
2. Edit the script in the database.
3. Run `./gradlew export.config.script`.

The export regenerates the whole file from the **local** database. Entries of processes, parameters or menus that
belong to bundles not installed locally come out as deletions, and `versionInfo` takes the local core version.
**Commit only the entries of the rows you changed**; never the deletions or the version change.

Full procedure: [Exporting Process JavaScript](https://github.com/etendosoftware/com.etendorx.workspace-ui/blob/main/docs/process/definition/exporting-process-js.md)
(`client/docs/process/definition/exporting-process-js.md` in the new UI repository).
