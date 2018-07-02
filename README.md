# cdrom_crc

This crate contains functions to calculate [CRCs (cyclic redundancy checks)](https://en.wikipedia.org/wiki/Cyclic_redundancy_check) as used in the CD-DA and CD-ROM standards.

## Introduction

The CD standards use [CRCs (cyclic redundancy checks)](https://en.wikipedia.org/wiki/Cyclic_redundancy_check)
as a way to allow a player to check for corruption of low-level metadata.
Since CDs are a physical medium that can suffer from scratches, dust, and other
damage, it's important to be able to know that playback metadata is actually
accurate before trying to read it.
While most developers will never touch this layer of a disc, developers
writing tools which create or modify raw disc images will need to be able
to create them.

The CD-DA and CD-ROM standards use two types of CRC functions in different
parts of each sector:

1. A 32-bit CRC within the error correction metadata located within each sector.
2. A 16-bit CRC within the second [subcode](https://en.wikipedia.org/wiki/Compact_Disc_subcode).

This crate currently only provides the 16-bit CRC.

