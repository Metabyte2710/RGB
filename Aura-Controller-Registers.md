This page is a work in progress.  Register and mode names are unofficial, I tried to name them based on what I think they do.  They're subject to change as well, though the values should be good.

# **AURA_REG_COLORS_DIRECT** 0x8000
15 bytes of color data beginning at this address for direct color control (AURA_REG_DIRECT = 1).

Format is RBGRBGRBGRBGRBG.  Each Aura controller supports up to 5 outputs.

# **AURA_REG_COLORS_EFFECT** 0x8010
15 bytes of color data beginning at this address for internal effects color control (AURA_REG_DIRECT = 0).

Format is RBGRBGRBGRBGRBG.  Each Aura controller supports up to 5 outputs.

# **AURA_REG_DIRECT** 0x8020
Set this register to 0 for Aura controller internally generated effects, set to 1 to directly set colors.  The two modes use different color banks - AURA_REG_COLORS_EFFECT if set 0 and AURA_REG_COLORS_DIRECT if set 1.

# **AURA_REG_MODE** 0x8021
This register selects the Aura controller effect.  It is ignored if AURA_REG_DIRECT is set to 1.  It accepts the following values:

### 0: **AURA_MODE_OFF**
Turns the lighting off.

### 1: **AURA_MODE_STATIC**
Static, constant color.

### 2: **AURA_MODE_BREATHING**
Slow fade from off to full brightness, then back to off.

### 3: **AURA_MODE_FLASHING**
Switches the lighting on, waits, then switches it off.  No fading.

### 4: **AURA_MODE_SPECTRUM_CYCLE**
Slowly fades through the color spectrum, all lights same color.

### 5 **AURA_MODE_RAINBOW**
Slowly fades through the color spectrum as a rainbow gradient across the 5 channels.

### 6 **AURA_MODE_SPECTRUM_CYCLE_BREATHING**
Same as Breathing effect, but every pulse increments slightly through the color spectrum.

### 7 **AURA_MODE_CHASE_FADE**
Lights chase across the 5 channels with a fade out effect.

### 8 **AURA_MODE_SPECTRUM_CYCLE_CHASE_FADE**
Same as Chase Fade effect, but every pulse increments slightly through the color spectrum.

### 9 **AURA_MODE_CHASE**
Lights flash across the 5 channels with no fade out effect.

### 10 **AURA_MODE_SPECTRUM_CYCLE_CHASE**
Same as Chase effect, but every pulse increments slightly through the color spectrum.

### 11 **AURA_MODE_SPECTRUM_CYCLE_WAVE**
A slower, wider version of the chase fade effect, with increments slightly through the color spectrum.

### 12 **AURA_MODE_CHASE_RAINBOW_PULSE**
A quick pulse shoots across the 5 channels, followed by a gradient fade across the channels that retreats in the same direction it started.  Color varies each cycle through the color spectrum.

### 13 **AURA_MODE_RANDOM_FLICKER**
Seemingly random flickers of light across the 5 channels, with increments slightly through the color spectrum.

# **AURA_REG_APPLY** 0x80A0
Write a 1 to this register to apply the settings in the other registers.  Changes do not apply immediately.