
# My shops https://keyboard-hoarders.com // https://keyboardhoarders.etsy.com
# Now change the keymap using ZMK.studio 
1. Go to zmk.studio
2. plug in left half of the keyboard via USB to computer
3. select USB once at zmk.studio
4. this will open a list of connected devices. Find CorneWireless and connect
5. Unlock keyboard by going to the last layer on your keyboard and use the zmk studio unlock key as shown in the keymap picture.

![il_fullxfull 6886024620_quu0 jpg](https://github.com/user-attachments/assets/8c71c6dc-2ea5-4970-923f-6727532cd4f8)


Want an easy way to customize the keymap?  I have a guide [https://www.keyboardhoarders.com/post/1288093071901/zmk-change-keymap-walkthrough](https://keyboard-hoarders.com/pages/guides-1)

<img width="900" height="1709" alt="my_keymap-3" src="https://github.com/user-attachments/assets/e7869ef1-371d-4beb-997a-2e57da00d3d9" />

#   Combo diagram.


<img width="915" height="2294" alt="combos" src="https://github.com/user-attachments/assets/0c39e4ee-ecda-4e94-934f-a7b5405323d7" />



How to switch bluetooth devices.

![bluetoothpair-guide](https://github.com/user-attachments/assets/d777bf4e-a7e3-4429-8638-2b11e7558153)

# Trackpad (Azoteq TPS43)

The right half can have an Azoteq TPS43 trackpad instead of a nice!view
display. It's wired through the PCB's OLED header (now free since this
half has no screen) plus two spare pads on the nice!nano itself:

| TPS43 pin | nice!nano pad |
|---|---|
| VDD | 3V (OLED header) |
| GND | GND (OLED header) |
| SDA | D2 (OLED header "SDA/MOSI" pad) |
| SCL | D3 (OLED header "SCL/SCK" pad) |
| RST | D8 |
| RDY | D9 |

After changing `config/west.yml` you'll need to run `west update` (or let
the GitHub Action do it) to pull in the trackpad driver module before
building.

Cursor movement, scrolling, tap-to-click, two-finger right-click,
press-and-hold drag, pinch-to-zoom, and 4-direction swipes all work out
of the box. If the cursor is inverted or the axes are swapped once you
flash it, adjust the commented-out `switch-xy` / `invert-x` / `invert-y`
/ `invert-scroll-y` properties in `config/corne_right.overlay` to match
how the module ends up mounted. Swipe/zoom shortcuts default to
macOS-style bindings; comment out the `TRACKPAD_MAC_MODE` define at the
top of `config/corne_left.overlay` for Windows/Linux-style shortcuts
instead.
