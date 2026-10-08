# 9base qFlipper downstream

**Status: Maintained Downstream; kept active.** Documentation reconstructed from repository history on 8 October 2026.

This is a downstream of [flipperdevices/qFlipper](https://github.com/flipperdevices/qFlipper), the Qt application for updating and interacting with Flipper Zero. The application, ordinary build instructions and upstream notices belong to the upstream project; 9base maintains the specific patch documented here.

## Verified patch

Süleyman Poyraz (GitHub `Zaryob`) authored [5117c9cb](https://github.com/9base/qFlipper/commit/5117c9cbebb874900d36ab87b251e2eb4269df75) on 22 May 2024, titled “Special hardware change.” In `backend/flipperzero/helper/deviceinfohelper.cpp`, the patch comments out the empty-device-name rejection in `VCPDeviceInfoHelper::fetchDeviceInfoLegacy` and `fetchDeviceInfoProperty`. Both paths continue through `advanceState()` when the name is empty. This describes the observed behavior; the specific hardware model, deployment and validation procedure are undocumented.

The retained patch is the only net source-file difference identified in the pre-curation comparison. It is compatibility behavior for this downstream, not a claim that upstream validation is universally unnecessary.

## Branch and synchronization evidence

The sole 9base branch is `dev`. [d7fcbd42](https://github.com/9base/qFlipper/commit/d7fcbd42031eab46255ec7beb57b0e2687ea1b51), dated 7 October 2026, merges upstream `dev` while retaining the local patch. Before documentation curation, the branch was two commits ahead of and none behind the audited upstream `dev` head: one technical patch and one merge. These are not two independent features.

The merge supports the maintained-downstream classification. A recurring synchronization cadence, specific target hardware and current testing policy have not been established; this record does not invent them. Existing upstream build instructions remain in [README.md](README.md). No source or build behavior was changed by archival documentation curation.
