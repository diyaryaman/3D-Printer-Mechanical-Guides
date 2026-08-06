# Vref Adjustment Guide

## Purpose
![Vref measurement](/image.png)

This guide explains how to safely adjust the **Vref (Reference Voltage)** of the four stepper driver channels.

The Vref adjustment points are the small potentiometers marked with red circles on the control board.

Reducing the Vref decreases the current supplied to the stepper motors. This can help:

- Reduce motor temperature
- Reduce stepper driver temperature
- Lower overall power consumption

However, reducing the Vref too much may result in:

- Skipped steps
- Reduced motor torque
- Unreliable motor movement
- Layer shifts or positioning errors during printing

For this reason, always make small adjustments and verify the printer operates normally after each change.

---

# Required Tools

Prepare the following equipment before starting:

- Digital multimeter capable of measuring DC voltage
- Ceramic or insulated precision screwdriver
- Stable power supply
- Pen, notebook, or spreadsheet for recording original values

---

# Safety Notes

Please read all safety information before making any adjustments.

- Never adjust the potentiometer without measuring the voltage.
- Avoid shorting nearby components with the screwdriver or multimeter probe.
- A ceramic or insulated screwdriver is strongly recommended.
- Make only very small adjustments.
- Always record the original Vref value before changing anything.
- Do not touch other parts of the PCB while power is applied.

> **Important Correction**

The board **must be powered ON** while measuring or adjusting Vref.

Power should only be disconnected while:

- Connecting the multimeter probes
- Choosing the ground point
- Changing wiring or probe connections

---

# Step-by-Step Procedure

## Step 1 — Prepare the Board (Power OFF)

Before touching the adjustment area:

1. Turn off the board.
2. Disconnect the main power supply.
3. Disconnect USB power.
4. Wait several seconds for the capacitors to discharge.
5. Connect the black multimeter probe to a reliable GND point while the board is still powered off.

---

## Step 2 — Locate the Vref Potentiometers

Locate the four potentiometers highlighted on the board.

Each potentiometer controls the Vref of one individual stepper driver channel.

Ensure you know which potentiometer belongs to each driver before making any adjustments.

---

## Step 3 — Configure the Multimeter

Set the multimeter to measure **DC Voltage**.

Recommended measurement ranges:

- 0–2 V DC
- 0–20 V DC

Any range capable of accurately measuring voltages around 1 V is acceptable.

---

## Step 4 — Verify the Ground Connection

Connect the black probe to a stable ground point.

Typical ground locations include:

- DC power connector negative pin
- USB-C shield
- GND pad
- Any verified ground point on the PCB

The probe should remain stable during the entire adjustment process.

---

## Step 5 — Power ON and Measure the Original Vref

Turn the board ON.

Place the red probe on the metal top of the potentiometer.

Measure and record the original voltage before making any adjustments.

Example:

```
Driver 1: 0.82 V
Driver 2: 0.81 V
Driver 3: 0.80 V
Driver 4: 0.83 V
```

Never skip this step.

Recording the original values allows you to safely restore them if necessary.

---

## Step 6 — Lower the Vref Slowly

Keep:

- The board powered ON
- The black probe connected to GND
- The multimeter monitoring the voltage continuously

Using an insulated screwdriver, rotate the potentiometer only a very small amount.

> In most boards, turning the potentiometer counter-clockwise reduces Vref, but this is **not guaranteed** for every board.

After every small adjustment:

1. Remove the screwdriver.
2. Read the new voltage.
3. Decide whether another small adjustment is necessary.

Recommended adjustment amount:

- Reduce approximately **0.03–0.05 V** at a time.

Avoid making large changes in a single adjustment.

Example:

```
Original: 0.82 V

First adjustment:
0.78 V

Second adjustment:
0.74 V
```

---

## Step 7 — Repeat for All Driver Channels

Repeat the same process for each of the four drivers.

Whenever possible, motors with similar mechanical loads should use similar Vref values.

Only use different Vref values when a specific motor requires a different operating current.

Example final measurements:

```
Driver 1: 0.74 V
Driver 2: 0.74 V
Driver 3: 0.75 V
Driver 4: 0.74 V
```

---

## Step 8 — Test the Printer

After all adjustments have been completed:

- Move every motor.
- Verify smooth motion.
- Listen for abnormal noise.
- Check for skipped steps.
- Confirm sufficient motor torque.
- Verify that motor and driver temperatures have improved.

If a motor skips steps or becomes weak:

Increase the Vref slightly and test again.

---

# Important Notes

Do not reduce the Vref more than necessary.

A Vref value that is too low may cause unreliable motor operation.

The ideal setting is:

> The lowest Vref value that still provides stable and reliable motor movement without skipped steps.

The correct final Vref depends on several factors, including:

- Stepper driver model
- Motor rated current
- Sense resistor value
- Required motor torque
- Cooling conditions

If both the driver IC model and sense resistor value are known, the motor current can be calculated much more accurately.

---

# Power State Summary

### Power OFF

Use this state when:

- Connecting probes
- Selecting the ground point
- Changing probe connections

---

### Power ON

Use this state when:

- Measuring Vref
- Monitoring the multimeter
- Making small Vref adjustments

Never attempt to measure Vref while the board is completely powered off.
