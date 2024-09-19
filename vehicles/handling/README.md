# FiveM Vehicle Handling Configuration

This document describes all possible parameters that can be found in a FiveM vehicle handling configuration file. These settings control various aspects of vehicle behavior, including acceleration, braking, suspension, and traction, across different vehicle types (cars, motorcycles, boats, planes, etc.).

## Table of Contents
- [Basic Vehicle Parameters](#basic-vehicle-parameters)
  - [Mass & Weight](#mass--weight)
  - [Aerodynamics](#aerodynamics)
- [Transmission & Drivetrain](#transmission--drivetrain)
- [Acceleration & Drive Force](#acceleration--drive-force)
- [Braking & Steering](#braking--steering)
- [Traction & Grip](#traction--grip)
- [Suspension Settings](#suspension-settings)
- [Damage & Collision](#damage--collision)
- [SubHandlingData](#subhandlingdata)
  - [Cars](#subhandlingdata-for-cars)
  - [Motorcycles](#subhandlingdata-for-motorcycles)
  - [Boats](#subhandlingdata-for-boats)
  - [Planes](#subhandlingdata-for-planes)
  - [Helicopters](#subhandlingdata-for-helicopters)
  - [Bikes (Bicycles)](#subhandlingdata-for-bikes-bicycles)
  
---

## Basic Vehicle Parameters

### Mass & Weight
- **`fMass`**: Vehicle weight in kilograms. Affects acceleration, braking, and cornering.
  - Example: `fMass value="1600.000000"`
  
- **`vecCentreOfMassOffset`**: Offsets the center of mass of the vehicle (x, y, z).
  - Example: `vecCentreOfMassOffset x="0.000000" y="0.000000" z="-0.100000"`

- **`fInertiaMultiplier`**: Affects how much the vehicle resists changes in motion (x, y, z).
  - Example: `fInertiaMultiplier x="1.000000" y="1.000000" z="1.000000"`

---

### Aerodynamics
- **`fInitialDragCoeff`**: Controls air resistance. Lower values mean less drag.
  - Example: `fInitialDragCoeff value="2.500000"`

- **`fPercentSubmerged`**: Percentage of the vehicle that must be submerged before it floats. Higher values mean the vehicle can stay underwater longer.
  - Example: `fPercentSubmerged value="85.000000"`

---

## Transmission & Drivetrain

- **`nInitialDriveGears`**: Number of gears in the vehicle’s transmission.
  - Example: `nInitialDriveGears value="6"`

- **`fDriveBiasFront`**: Bias of power distribution between the front and rear wheels. 1.0 = Front-wheel drive, 0.0 = Rear-wheel drive.
  - Example: `fDriveBiasFront value="0.300000"`

- **`fClutchChangeRateScaleUpShift`**: Speed of gear changes when shifting up.
  - Example: `fClutchChangeRateScaleUpShift value="2.500000"`

- **`fClutchChangeRateScaleDownShift`**: Speed of gear changes when shifting down.
  - Example: `fClutchChangeRateScaleDownShift value="2.500000"`

---

## Acceleration & Drive Force

- **`fInitialDriveForce`**: Determines how much force the vehicle uses to accelerate.
  - Example: `fInitialDriveForce value="0.320000"`

- **`fDriveInertia`**: Resistance to changes in speed when accelerating or decelerating.
  - Example: `fDriveInertia value="1.000000"`

- **`fInitialDriveMaxFlatVel`**: Maximum speed in meters per second.
  - Example: `fInitialDriveMaxFlatVel value="150.000000"`

---

## Braking & Steering

- **`fBrakeForce`**: Strength of the braking force.
  - Example: `fBrakeForce value="0.800000"`

- **`fBrakeBiasFront`**: Distribution of brake force between the front and rear wheels. 1.0 = Front, 0.0 = Rear.
  - Example: `fBrakeBiasFront value="0.500000"`

- **`fHandBrakeForce`**: Strength of the handbrake.
  - Example: `fHandBrakeForce value="0.700000"`

- **`fSteeringLock`**: Maximum angle of the steering wheel (in degrees).
  - Example: `fSteeringLock value="35.000000"`

---

## Traction & Grip

- **`fTractionCurveMax`**: Maximum level of traction during cornering.
  - Example: `fTractionCurveMax value="2.000000"`

- **`fTractionCurveMin`**: Minimum level of traction during cornering.
  - Example: `fTractionCurveMin value="1.500000"`

- **`fTractionBiasFront`**: Distribution of traction between front and rear wheels. 1.0 = Front, 0.0 = Rear.
  - Example: `fTractionBiasFront value="0.400000"`

- **`fLowSpeedTractionLossMult`**: Multiplier for how much traction is lost at low speeds.
  - Example: `fLowSpeedTractionLossMult value="0.500000"`

---

## Suspension Settings

- **`fSuspensionForce`**: Stiffness of the suspension. Higher values = stiffer suspension.
  - Example: `fSuspensionForce value="2.500000"`

- **`fSuspensionCompDamp`**: Dampening when the suspension is compressed.
  - Example: `fSuspensionCompDamp value="1.000000"`

- **`fSuspensionReboundDamp`**: Dampening when the suspension rebounds after compression.
  - Example: `fSuspensionReboundDamp value="1.000000"`

- **`fSuspensionRaise`**: How much the suspension is raised.
  - Example: `fSuspensionRaise value="0.000000"`

- **`fSuspensionBiasFront`**: Suspension balance between the front and rear.
  - Example: `fSuspensionBiasFront value="0.500000"`

---

## Damage & Collision

- **`fCollisionDamageMult`**: Multiplier for damage taken during collisions.
  - Example: `fCollisionDamageMult value="0.200000"`

- **`fWeaponDamageMult`**: Multiplier for damage taken from weapons.
  - Example: `fWeaponDamageMult value="1.000000"`

- **`fDeformationDamageMult`**: Multiplier for how much the vehicle deforms on impact.
  - Example: `fDeformationDamageMult value="0.700000"`

---

## SubHandlingData

The `SubHandlingData` section allows for more specialized handling configurations for specific vehicle types, including cars, motorcycles, boats, planes, and helicopters.

### SubHandlingData for Cars
- **`fBackEndPopUpCarImpulseMult`**: Controls the lift of the back end of the car during high-acceleration situations.
  - Example: `fBackEndPopUpCarImpulseMult value="0.100000"`

- **`fToeFront`**: Front wheel alignment, affecting stability during cornering.
  - Example: `fToeFront value="0.010000"`

- **`fCamberFront` & `fCamberRear`**: Determines how much the front and rear wheels tilt inward or outward.
  - Example: `fCamberFront value="-0.500000"`

---

### SubHandlingData for Motorcycles
- **`fLeanFwdForceMult`**: Multiplier for the force when leaning forward.
  - Example: `fLeanFwdForceMult value="10.000000"`

- **`fWheelieBalancePoint`**: Angle at which the motorcycle maintains balance during a wheelie.
  - Example: `fWheelieBalancePoint value="10.000000"`

- **`fMaxBankAngle`**: Maximum angle the motorcycle can lean while turning.
  - Example: `fMaxBankAngle value="55.000000"`

---

### SubHandlingData for Boats
- **`fThrust`**: Engine thrust, controlling acceleration for boats.
  - Example: `fThrust value="8.000000"`

- **`fWaterResistance`**: Controls the drag on the boat in water.
  - Example: `fWaterResistance value="0.020000"`

- **`fWaveAudioMult`**: Controls how much sound is generated from waves.
  - Example: `fWaveAudioMult value="1.000000"`

---

### SubHandlingData for Planes
- **`fThrust`**: Engine thrust for airplanes, controlling how fast the plane can accelerate.
  - Example: `fThrust value="10.000000"`

- **`fLiftForce`**: The force that lifts the airplane during takeoff.
  - Example: `fLiftForce value="1.500000"`

- **`fYawMult`**: Multiplier for how responsive the airplane is when yawing (turning left or right).
  - Example: `fYawMult value="1.
