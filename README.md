# SilentOS for Badger2040

It's a simple state machine for switching between different applications on Badger2040.

Implemented using MicroPython, all apps are supposed to be MicroPython modules.

## How to use
1. Develop your own application. Application is a MicroPython module with `app_` prefix and implementing the next 4 functions:
     - `enter(display: badger2040.Badger2040) -> None`: called when the OS loads up the application
     - `process_a(display: badger2040.Badger2040) -> None`: called when the user presses the A button
     - `process_b(display: badger2040.Badger2040) -> None`: called when the user presses the B button
     - `process_c(display: badger2040.Badger2040) -> None`: called when the user presses the C button

2. Upload SilentOS files (`main.py` and `utils.py`) to the Badger2040 together with your apps
3. Each time when you press UP or DOWN buttons, the OS switches to the next or previous application respectively
4. Each time when you press A, B or C buttons, the OS calls the corresponding function of the current application