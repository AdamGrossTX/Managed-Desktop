---
title: Windows quality update signals
description: This article explains the Windows quality update signals
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentation
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
manager: dougeby
ms.topic: conceptual
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
---

# Windows quality update signals

Microsoft Managed Desktop monitors a specific set of signals and aims to release quality updates both quickly and safely. The service doesn't comprehensively monitor every use case in Windows.

If there's a scenario that is critical to your business, which isn't monitored by Microsoft Managed Desktop, you're responsible for testing and taking any follow-up actions, like requesting to pause the release.

## Pre-release signals

Before being released to the Test ring, Microsoft Managed Desktop reviews several data sources to determine if we need to send any customer advisories or need to pause the update. Situations where Microsoft Managed Desktop doesn't release an update to the Test ring are seldom occurrences.

| Pre-release signal | Description |
| ----- | ----- |
| Windows Payload Review | The contents of the B release are reviewed to help focus your update testing on areas that have changed. If any relevant changes are detected, a [customer advisory](../operate/update-communications.md#communications-during-release) will be sent out. |
| C-Release Review - Internal Signals | Microsoft Managed Desktop reviews active incidents associated with the previous C release to understand potential risks in the B release. |
| C-Release Review - Social Signals | Microsoft Managed Desktop monitors social signals to better understand potential risks associated with the B release. |

## Early signals

The update is released to the Test ring on the second Tuesday of the month. Those test devices will update, allowing you to conduct early testing of critical scenarios in your environment. There are also several new Microsoft internal signals that have become available to the service that are monitored throughout the release.

| Device reliability signal | Description | Microsoft will |
| ----- | ----- | ----- |
| Security Risk Profile | As soon as the update is released, the criticality of the security content is assessed. | <ul><li>Consider expediting the release</li><li>Update customers with a risk profile</li></ul>
| B-Release - Internal Signals | Microsoft Managed Desktop reviews any active incidents associated with the current release. | <ul><li>Determine if a customer advisory is necessary</li><li>Pause the release if there's significant user impact</li></ul> |
| B-Release - Social Signals | Microsoft Managed Desktop monitors social signals to understand risks associated with the release. | Determine if a customer advisory is necessary |

## Device reliability signals

Microsoft Managed Desktop monitors devices for a set of core reliability metrics as a part of the service.

The service then uses statistical models to assess if there are significant differences between the two Windows versions. To make a statistically significant assessment, Microsoft Managed Desktop requires that at least 500 devices in your tenant have upgraded to the new version.

As more devices update, the confidence of the analysis increases and gives us a clearer picture of release quality. If we determine that the user experience is impaired, MIcrosoft Managed Desktop will either post a customer advisory or pause the release, depending on the criticality of the update.

Microsoft Managed Desktop monitors the following reliability signals:

| Device reliability signal | Description |
| ----- | ----- |
| Blue screens | These events are highly disruptive to end users. These events are closely monitored. |
| Overall app reliability | Tracks the total number of app crashes and freezes on a device. A known limitation with this measure is that if one app becomes 10% more reliable and another becomes 10% less reliable then it shows up as a flat line in the measure. |
| Microsoft Office reliability | Tracks the number of Office crashes and freezes per application per device. |
| Microsoft Edge reliability | Tracks the number of Microsoft Edge crashes and freezes per device. |
| Microsoft Teams reliability | Tracks the number of Microsoft Teams crashes and freezes per device. |

When the update is released to the First ring, the service crosses the 500 device threshold. Therefore, Microsoft Managed Desktop can to detect regressions, which are common to all customers. At this point in the release, we'll decide if we need to change the release schedule or pause for all customers.
