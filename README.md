# icePie FPGA devkit - RiscV Examples

Examples codes demonstrating implementation of RiscV softcores on the icePie FPGA devkit.

## Requirements

* [oss-cad-suite](https://github.com/YosysHQ/oss-cad-suite-build/releases)
  
  Download the package suited for your architecture (typically `x64`). Decompress the package and run `source environment` inside the `oss-cad-suite` directory.

  Add the bin directory to PATH in .bash_profile (ex: `export PATH=$PATH:~/fpga/oss-cad-suite/bin`).

* [xpack-tools-riscv-gcc](https://github.com/xpack-dev-tools/riscv-none-elf-gcc-xpack/releases/)

  Download the package suited for your architecture (typically `x64`). 
  
  Add the bin directory to PATH in .bash_profile (ex: `export PATH=$PATH:~/fpga/xpack-riscv-none-elf-gcc-12.2.0-3/bin`).

## Projects

* [picorv32](https://github.com/YosysHQ/picorv32)/[picosoc](https://github.com/YosysHQ/picorv32/tree/master/picosoc)

  Run `make icepieprog` from `picorv32/picosoc` directory.

  Use terminal program on `/dev/ttyUSB1` with baudrate 115200 (ex: `miniterm.py /dev/ttyUSB1 115200`) to see the processor output. 
  
  `picorv32/picosoc/firmware.c` contains the embedded C code for the firmware being executed. 

* [learn-fpga](https://github.com/BrunoLevy/learn-fpga)/[FemtoRV](https://github.com/BrunoLevy/learn-fpga/tree/master/FemtoRV)
  
  Configure the peripherals (LEDs, UART, OLED(SPI via PMOD), SDCARD, MAX7219 LED Matrix, etc) by editing `learn-fpga/FemtoRV/RTL/CONFIGS/icepie_config.v`. Refer to [FemtoRV Icebreaker Tutorial](https://github.com/BrunoLevy/learn-fpga/blob/master/FemtoRV/TUTORIALS/IceBreaker.md).
  
  Run `make ICEPIE` from `learn-fpga/FemtoRV` directory for programming the FPGA bitstream.

  Run `make hello.prog` from `learn-fpga/FemtoRV/FIRMWARE/EXAMPLES` for compiling and loading `hello.c` program present in the same directory. Use terminal program on `/dev/ttyUSB1` with baudrate 115200 (ex: `miniterm.py /dev/ttyUSB1 115200`) to see the processor output.

  Similar examples programs can be found within `learn-fpga/FemtoRV/FIRMWARE/ASM_EXAMPLES`. Run `make <program name>.prog` for both C and ASM files listed below.

  | Program                 	     	  	        | Description            		  | Peripheral           |
  |-----------------------------------------------------|-----------------------------------------|----------------------|
  | `FIRMWARE/EXAMPLES/hello.c`      		        | Hello, World program           	  | UART                 |
  | `FIRMWARE/EXAMPLES/hello_LED.c`  	  		| Hello, World program on LED matrix  	  | MAX7219 LED Matrix   |
  | `FIRMWARE/EXAMPLES/pi.c`         	 		| Pi value computation 		  	  | UART	         |
  | `FIRMWARE/EXAMPLES/sieve.c`     	  		| Sieve of Eratosthenes           	  | UART                 |
  | `FIRMWARE/EXAMPLES/test_buttons.c`    		| Button Test           		  | Buttons, Encoder     |
  | `FIRMWARE/EXAMPLES/test_spi_sdcard.c` 		| SD card FAT32 FS Test           	  | SD card, UART        |
  | `FIRMWARE/ASM_EXAMPLES/hello.S`  	  		| Hello, World program  	   	  | UART		 |
  | `FIRMWARE/ASM_EXAMPLES/test_serial.S`  		| UART echo and 4 LSBs to LED  	   	  | UART, LEDs		 |
  | `FIRMWARE/ASM_EXAMPLES/mandelbrot_terminal.S`  	| Mandelbrot Fractal on Terminal  	  | UART	         |
  | `FIRMWARE/ASM_EXAMPLES/blinker_*.S`  	        | LED Blinker		    	          | LEDs	         |

  Various other programs present in the `FIRMWARE` can be run with SPI OLED display (SSD1331/SSD1351). Configure the board with appropriate settings as mentioned in the first step.

## Licenses

  Applicable license is individual to each IP core / project and is mentioned in the IP core / example directory itself and in each file.


