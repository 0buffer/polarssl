# mbed TLS Benchmark Example

This application benchmarks the various cryptographic primitives offered by mbed TLS.

## Pre-requisites

To build and run this example you must have:

* A computer with the following software installed:
  * [CMake](http://www.cmake.org/download/).
  * [yotta](https://github.com/ARMmbed/yotta). Please note that **yotta has its own set of dependencies**, listed in the [installation instructions](http://armmbed.github.io/yotta/#installing-on-windows).
  * [Python](https://www.python.org/downloads/).
  * [The ARM GCC toolchain](https://launchpad.net/gcc-arm-embedded).
  * A serial terminal emulator (Like screen, pySerial and cu).
* An [FRDM-K64F](http://developer.mbed.org/platforms/FRDM-K64F/) development board, or another board supported by mbed OS (in which case you'll have to substitute frdm-k64f-gcc with the appropriate target in the instructions below).
* A micro-USB cable.
* If your OS is Windows, please follow the installation instructions [for the serial port driver](https://developer.mbed.org/handbook/Windows-serial-configuration).

## Getting started

1. Connect the FRDM-K64F to the computer with the micro-USB cable, being careful to use the "OpenSDA" connector on the target board.

2. Navigate to the mbedtls directory supplied with your release and open a terminal.

3. Set the yotta target:

    ```
    yotta target frdm-k64f-gcc
    ```

4. Build mbedtls and the examples. This may take a long time if this is your first compilation:

    ```
    $ yotta build
    ```

5. Copy `build/frdm-k64f-gcc/test/mbedtls-test-example-benchmark.bin` to your mbed board and wait until the LED next to the USB port stops blinking.

6. Start the serial terminal emulator and connect to the virtual serial port presented by FRDM-K64F. 

	Use the following settings:

	* 115200 baud (not 9600).
	* 8N1.
	* No flow control. 

7. Press the Reset button on the board.

8. The output in the terminal window should look like:

    ```
    {{timeout;150}}
    {{host_test_name;default}}
    {{description;mbed TLS benchmark program}}
    {{test_id;MBEDTLS_BENCHMARK}}
    {{start}}


      SHA-1                    :       3644 Kb/s,         32 cycles/byte
      SHA-256                  :       1957 Kb/s,         59 cycles/byte
      SHA-512                  :        587 Kb/s,        200 cycles/byte
      AES-CBC-128              :       1359 Kb/s,         86 cycles/byte
      AES-CBC-192              :       1183 Kb/s,         99 cycles/byte
      AES-CBC-256              :       1048 Kb/s,        111 cycles/byte
      AES-GCM-128              :        421 Kb/s,        279 cycles/byte
      AES-GCM-192              :        403 Kb/s,        292 cycles/byte
      AES-GCM-256              :        385 Kb/s,        305 cycles/byte
      AES-CCM-128              :        542 Kb/s,        216 cycles/byte
      AES-CCM-192              :        484 Kb/s,        242 cycles/byte
      AES-CCM-256              :        437 Kb/s,        268 cycles/byte
      CTR_DRBG (NOPR)          :       1002 Kb/s,        117 cycles/byte
      CTR_DRBG (PR)            :        705 Kb/s,        166 cycles/byte
      HMAC_DRBG SHA-1 (NOPR)   :        228 Kb/s,        517 cycles/byte
      HMAC_DRBG SHA-1 (PR)     :        210 Kb/s,        561 cycles/byte
      HMAC_DRBG SHA-256 (NOPR) :        212 Kb/s,        557 cycles/byte
      HMAC_DRBG SHA-256 (PR)   :        185 Kb/s,        637 cycles/byte
      RSA-2048                 :      41 ms/ public
      RSA-2048                 :    1349 ms/private
      RSA-4096                 :     134 ms/ public
      RSA-4096                 :    7149 ms/private
      ECDSA-secp384r1          :     640 ms/sign
      ECDSA-secp256r1          :     387 ms/sign
      ECDSA-secp384r1          :    1233 ms/verify
      ECDSA-secp256r1          :     751 ms/verify
      ECDHE-secp384r1          :    1191 ms/handshake
      ECDHE-secp256r1          :     730 ms/handshake
      ECDHE-Curve25519         :     611 ms/handshake
      ECDH-secp384r1           :     584 ms/handshake
      ECDH-secp256r1           :     365 ms/handshake
      ECDH-Curve25519          :     303 ms/handshake

    {{success}}
    {{end}}
    ```
[None] Edit by 'iter_edit_files'[None] Edit by 'iter_edit_files'[None] Edit by 'iter_edit_files'[None] Edit by 'iter_edit_files'[None] Edit by 'iter_edit_files'[None] Edit by 'iter_edit_files'