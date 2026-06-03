# UrbanCKM
UrbanCKM Dataset

# Dataset Description

## 1. Dataset Overview

This dataset contains channel-related information generated under multiple urban communication scenarios. Each scenario is stored in an independent folder, and each scenario folder contains a multi-sheet Excel file named:

dod_doa_phi_theta_pl_los_tx_rx.xlsx

The dataset provides multi-path angular information, path loss information, line-of-sight labels, and transmitter/receiver coordinates. It can be used for channel knowledge map construction, channel parameter prediction, graph-based channel reconstruction, and wireless environment-aware learning tasks.

---

## 2. Folder Organization

The dataset is organized as follows:


This directory contains multiple scenario folders, such as:

* c11
* c12
* c13
* ...
* c64
* Geo_WenChang

The scenario indices may not be continuous. Each folder whose name starts with “c” represents one independent wireless propagation scenario.
The Geo_WenChang folder denotes a real-world geomorphic scenario in Wenchang, where the environmental information is acquired by UAV-based terrain data collection.

In addition, the root directory contains:

| File          | Description                                  |
| ------------- | -------------------------------------------- |
| receiver.xlsx | Coordinates of all receiver points           |
| obs.xlsx      | Obstacle information for different scenarios |

Each scenario folder contains:

| File                                | Description                                      |
| ----------------------------------- | ------------------------------------------------ |
| dod_doa_phi_theta_pl_los_tx_rx.xlsx | Channel parameter table for the current scenario |

---

## 3. Scenario File Structure

For each scenario folder, the file dod_doa_phi_theta_pl_los_tx_rx.xlsx contains multiple sheets.

Each sheet corresponds to one transmitter.

For example:

| Sheet Name | Description                                 |
| ---------- | ------------------------------------------- |
| t001       | Channel data corresponding to transmitter 1 |
| t002       | Channel data corresponding to transmitter 2 |
| t003       | Channel data corresponding to transmitter 3 |
| ...        | Other transmitters                          |

In each sheet, each row corresponds to one receiver point.

Therefore, the data organization can be summarized as:

* One folder corresponds to one scenario.
* One Excel file corresponds to one scenario.
* One sheet corresponds to one transmitter.
* One row corresponds to one receiver point.

---

## 4. Column Description of dod_doa_phi_theta_pl_los_tx_rx.xlsx

Each row contains 23 columns. The detailed column definitions are listed below.

| Column Index | Description               |
| ------------ | ------------------------- |
| 1            | DOD phi of the 1st path   |
| 2            | DOD phi of the 2nd path   |
| 3            | DOD phi of the 3rd path   |
| 4            | DOD theta of the 1st path |
| 5            | DOD theta of the 2nd path |
| 6            | DOD theta of the 3rd path |
| 7            | DOA phi of the 1st path   |
| 8            | DOA phi of the 2nd path   |
| 9            | DOA phi of the 3rd path   |
| 10           | DOA theta of the 1st path |
| 11           | DOA theta of the 2nd path |
| 12           | DOA theta of the 3rd path |
| 13           | Total path loss           |
| 14           | Path loss of the 1st path |
| 15           | Path loss of the 2nd path |
| 16           | Path loss of the 3rd path |
| 17           | LOS label                 |
| 18           | Tx x-coordinate           |
| 19           | Tx y-coordinate           |
| 20           | Tx z-coordinate           |
| 21           | Rx x-coordinate           |
| 22           | Rx y-coordinate           |
| 23           | Rx z-coordinate           |

---

## 5. Angular Parameters

Columns 1–6 store the departure angle information, namely DOD.

| Columns | Description                        |
| ------- | ---------------------------------- |
| 1–3     | DOD phi of the first three paths   |
| 4–6     | DOD theta of the first three paths |

Columns 7–12 store the arrival angle information, namely DOA.

| Columns | Description                        |
| ------- | ---------------------------------- |
| 7–9     | DOA phi of the first three paths   |
| 10–12   | DOA theta of the first three paths |

The angular parameters are stored in radians. The first three propagation paths are retained for each transmitter–receiver pair.

---

## 6. Path Loss Parameters

Column 13 stores the total path loss of the transmitter–receiver pair.

Columns 14–16 store the path loss values of the first three propagation paths.

| Columns | Description               |
| ------- | ------------------------- |
| 13      | Total path loss           |
| 14      | Path loss of the 1st path |
| 15      | Path loss of the 2nd path |
| 16      | Path loss of the 3rd path |

These columns describe the large-scale and path-level attenuation characteristics of the wireless channel.

---

## 7. LOS Label

Column 17 stores the LOS label.

| Value | Description    |
| ----- | -------------- |
| 1     | LOS condition  |
| 0     | NLOS condition |

The LOS label indicates whether a line-of-sight propagation condition exists between the transmitter and the receiver.

---

## 8. Transmitter and Receiver Coordinates

Columns 18–20 store the transmitter coordinates.

| Columns | Description     |
| ------- | --------------- |
| 18      | Tx x-coordinate |
| 19      | Tx y-coordinate |
| 20      | Tx z-coordinate |

Columns 21–23 store the receiver coordinates.

| Columns | Description     |
| ------- | --------------- |
| 21      | Rx x-coordinate |
| 22      | Rx y-coordinate |
| 23      | Rx z-coordinate |

The coordinate information is used to describe the spatial relationship between transmitters, receivers, and the surrounding environment.

---

## 9. Obstacle Information

The file obs.xlsx stores the obstacle information for each scenario.

Each sheet in obs.xlsx corresponds to one scenario. For example, the sheet c11 corresponds to the scenario folder c11.

Each row in a sheet describes one obstacle. The columns are organized as follows:

| Column Index | Description                  |
| ------------ | ---------------------------- |
| 1            | Obstacle length              |
| 2            | Obstacle width               |
| 3            | Obstacle height              |
| 4            | Obstacle center x-coordinate |
| 5            | Obstacle center y-coordinate |
| 6            | Obstacle center z-coordinate |

The obstacle information can be used to characterize the physical environment and support environment-aware channel modeling.

---

## 10. Receiver Coordinate File

The file receiver.xlsx stores the coordinates of all receiver points.

| Column Index | Description     |
| ------------ | --------------- |
| 1            | Rx x-coordinate |
| 2            | Rx y-coordinate |
| 3            | Rx z-coordinate |

The receiver coordinate file provides the spatial sampling grid used in each scenario.

---

## 11. Summary

The dataset provides a structured representation of wireless channel parameters under different urban scenarios. Each scenario contains transmitter-specific channel information, where each row corresponds to one receiver point. The dataset includes multi-path DOD and DOA information, total path loss, path-level path loss, LOS labels, and transmitter/receiver coordinates, making it suitable for channel knowledge map construction and environment-aware wireless channel prediction.

