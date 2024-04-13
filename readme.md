# Backfire helix antenna for L and S band weather satellites

This feed is suitable for deep prime focus dishes having f/D ratio around 0.3-0.5. The polarization is LHCP made for RHCP satellites since the dish flips the polarization.

Please read carefully the notes below before you start building it!

![NEC4](pictures/feed_assembled.jpg)


## Background

The original "Wifi" grid dish or Nooelec grid dish comes with a linear polarized feed, but L-band weather satellites have circularly polarized signals. So I wanted to make a circular polarized feed to get that extra 3dB due to polarization mismatch. After reading a lot about antenna feeds, I chose this feed as it has very good properties and it is easy to build. After simulating and testing it, it proved to work great on my setup. (I have tested it against a dipole feed tuned to 1.7Ghz that comes with the Nooelec grid dish, and I have got around 3db better SNR)

This Backfire helix design is based on Hisamatsu Nakano, Junji Yamauchi, Hiroaki Mimaki: Backfire Radiation from a Monofilar Helix with a Small Ground Plane, IEEE TRANSACTIONS ON ANTENNAS AND PROPAGATION, VOL. 36, NO. 10, OCTOBER 1988

Another good resource is [W1Ghz antenna book](http://www.w1ghz.org/antbook/contents.htm).

The scaffold design is based on Dereksgc helix design.

## Important notes

- You can find the PCB gerber files for the backplate in the gerber folder. If you decide to make the PCB, it should fit tightly into the antenna scaffold, if not use sandpaper or a sharp knife to make the hole bigger. The SMA connector for the PCB is https://eu.mouser.com/ProductDetail/712-CONSMA001-C-G or similar.

- The size of the back plate plays an important role in the feed pattern! Making whatever size will not work! For the same reason any metalic material around the backplate could reduce the feed performance, so it is the best to hold the feed from underneath, probably anything smaller than the backplate will not change the feed characteristics. I haven't tried to use metalic arm yet, I only tested it with the 3D printed arm and with PVC tube.

- The feed impedance is around 150 ohm, you need to tune it to 50 ohm, otherwise you will have mismatch and you loose signal. A good VSWR ~1.2 can be achieved with adding a tuning element.
For antenna matching you need to a have a VNA. Just placing a random wire to the antenna will not work!
Matching the antenna takes time and practice, you have to play with the wire distance from the backplate, the tuning element length, tuning element distance from ground plate and the tuning element distance from the center. See pictures for a reference.

- You need to have the possible shortest cable between the feed and the LNA, any loss before the LNA will increase the noise. Use a good quality coax cable, or you can make your own arm and fit an LNA right below the backplate.

- Since I have dish from nooelec, the arm is designed for it. If you have a different dish, you need to design your own arm! The focus point of this feed is not the same as the original dipole feed. You need to find the correct spot by testing.

- While the helix is a wideband antenna, the backfire helix radiation pattern is greatly depends on the frequency. This design works great around 1650-1800Mhz.

- Holes on the scaffold for is made for ~1.2mm wire.

- Holes for holding together the arm and the feed are for M3 bolts. You can use cable tiers too.

## Tuning pictures

![NEC4](pictures/tune1.jpg)

![NEC4](pictures/tune2.jpg)

![NEC4](pictures/vswr.jpg)

## Simulation result

### NEC4 simulation with NEC2 engine 

![NEC4](pictures/simulation.png)

### Dish efficiency using W1GHZ's feedpattern calculator

![Dish efficiency](pictures/feedpattern.png)

## Future

An LNA circuit could be made on the back plate. Comming soon!