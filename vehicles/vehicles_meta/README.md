# Vehicle Configuration Guide (vehicles.meta)

This document provides an explanation for configuring vehicles in the `vehicles.meta` file for GTA V and FiveM, covering cars, trucks, SUVs, and motorcycles.

## Table of Contents
- [Introduction](#introduction)
- [Structure Overview](#structure-overview)
- [Elements Explained](#elements-explained)
  - [modelName](#modelname)
  - [txdName](#txdname)
  - [handlingId](#handlingid)
  - [gameName](#gamename)
  - [vehicleMakeName](#vehiclemakename)
  - [layout](#layout)
  - [cameraName](#cameraname)
  - [flags](#flags)
  - [type](#type)
  - [plateType](#platetype)
  - [vehicleClass](#vehicleclass)
  - [wheelType](#wheeltype)
- [Vehicle Specific Settings](#vehicle-specific-settings)
  - [Motorcycles](#motorcycles)
  - [Cars](#cars)
  - [Trucks](#trucks)
  - [SUVs](#suvs)
- [Conclusion](#conclusion)

---

## Introduction

The `vehicles.meta` file is critical in GTA V and FiveM to define vehicle behavior, appearance, handling, and other characteristics. Different vehicles have different configurations, including custom settings for cars, trucks, SUVs, and motorcycles.

## Structure Overview

```xml
<CVehicleModelInfo__InitDataList>
  <residentTxd>vehshare</residentTxd>
  <residentAnims />
  <InitDatas>
    <!-- Vehicle Data Configuration -->
  </InitDatas>
  <txdRelationships>
    <!-- Texture Dictionary Relationships -->
  </txdRelationships>
</CVehicleModelInfo__InitDataList>
```

- **residentTxd**: Defines shared textures used by vehicles.
- **InitDatas**: Contains the main vehicle configurations such as model name, handling ID, camera setups, etc.
- **txdRelationships**: Maps texture dictionary relationships between the parent and child vehicles.

## Elements Explained

### modelName
```xml
<modelName>bmws</modelName>
```
Defines the internal model name of the vehicle. For example, "bmws" represents a BMW motorcycle.

### txdName
```xml
<txdName>bmws</txdName>
```
Specifies the texture dictionary name for the vehicle.

### handlingId
```xml
<handlingId>BMWS</handlingId>
```
Links the vehicle to the corresponding handling data in the `handling.meta` file.

### gameName
```xml
<gameName>S1000</gameName>
```
This defines the in-game display name for the vehicle.

### vehicleMakeName
```xml
<vehicleMakeName>BMW</vehicleMakeName>
```
The make or manufacturer of the vehicle.

### layout
```xml
<layout>LAYOUT_BIKE_SPORT_BATI</layout>
```
Defines the seating and layout configuration. For motorcycles, "LAYOUT_BIKE_SPORT_BATI" is used.

### cameraName
```xml
<cameraName>FOLLOW_BIKE_CAMERA</cameraName>
```
Defines the camera settings for when the vehicle is being driven.

### flags
```xml
<flags>FLAG_NO_BOOT FLAG_IGNORE_ON_SIDE_CHECK FLAG_AVERAGE_CAR FLAG_HEADLIGHTS_USE_ACTUAL_BONE_POS</flags>
```
Flags control the features and properties of the vehicle. Different vehicles may use various flags.

### type
```xml
<type>VEHICLE_TYPE_BIKE</type>
```
Specifies the type of the vehicle, such as bike, car, truck, or SUV.

### plateType
```xml
<plateType>VPT_BACK_PLATES</plateType>
```
Defines the license plate type. For motorcycles, `VPT_BACK_PLATES` is typically used, while cars and trucks might use front and back plates.

### vehicleClass
```xml
<vehicleClass>VC_MOTORCYCLE</vehicleClass>
```
Defines the class of the vehicle. Motorcycles use `VC_MOTORCYCLE`, while cars and trucks use `VC_COMPACT`, `VC_SUV`, `VC_TRUCK`, etc.

### wheelType
```xml
<wheelType>VWT_BIKE</wheelType>
```
Defines the type of wheels for the vehicle. For motorcycles, it is `VWT_BIKE`, while cars and trucks will have their own types like `VWT_CAR` or `VWT_TRUCK`.

---

## Vehicle Specific Settings

### Motorcycles
Motorcycles require specific configurations for handling and camera perspectives. Example:
```xml
<layout>LAYOUT_BIKE_SPORT_BATI</layout>
<cameraName>FOLLOW_BIKE_CAMERA</cameraName>
<flags>FLAG_NO_BOOT FLAG_AVERAGE_CAR</flags>
<wheelType>VWT_BIKE</wheelType>
```
- **Layout**: Defines how the driver sits and interacts.
- **Cameras**: Set up specific cameras for motorcycles.
- **Flags**: Ensure that motorcycles don’t use car-related features like trunk checks.

### Cars
Cars have different layouts, cameras, and handling flags. Example:
```xml
<layout>LAYOUT_STD_MEDIUM</layout>
<cameraName>FOLLOW_CAR_CAMERA</cameraName>
<flags>FLAG_HAS_BOOT FLAG_AVERAGE_CAR</flags>
<type>VEHICLE_TYPE_CAR</type>
<wheelType>VWT_CAR</wheelType>
```
- **Layout**: Different types such as `LAYOUT_STD_COMPACT` for smaller cars and `LAYOUT_STD_MEDIUM` for mid-size.
- **Flags**: `FLAG_HAS_BOOT` ensures the car has a functioning trunk.
- **Wheel Type**: Defines regular car wheels.

### Trucks
Trucks are larger and typically use heavier handling configurations and different wheel setups.
```xml
<layout>LAYOUT_TRUCK</layout>
<cameraName>FOLLOW_TRUCK_CAMERA</cameraName>
<flags>FLAG_LARGE FLAG_HAS_TRAILER FLAG_HAS_BOOT</flags>
<type>VEHICLE_TYPE_TRUCK</type>
<wheelType>VWT_TRUCK</wheelType>
```
- **Flags**: Set `FLAG_HAS_TRAILER` if the truck can attach a trailer.
- **Type**: Defines this as a truck with a heavier physics model.

### SUVs
SUVs tend to have robust configurations for off-road capabilities. Example:
```xml
<layout>LAYOUT_SUV</layout>
<flags>FLAG_HAS_BOOT FLAG_AVERAGE_CAR FLAG_ALL_WHEEL_DRIVE</flags>
<type>VEHICLE_TYPE_SUV</type>
<wheelType>VWT_SUV</wheelType>
```
- **Layout**: Custom layout for SUVs.
- **Flags**: Enable features like all-wheel drive with `FLAG_ALL_WHEEL_DRIVE`.

---

