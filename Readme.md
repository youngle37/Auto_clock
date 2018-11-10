# Auto clock in/out on NCU HumanSys

## Dependency
 - Python3
 - requests
 - lxml

## How to Use
 1. 
    Make sure you have installed the dependencies.
    ```
        $ pip3 install requests lxml
    ```

 2. 
    Set these parameters in config.py

    | Parameters             | description                                                   |
    |------------------------|---------------------------------------------------------------|
    | account                | Account on Portal                                             |
    | password               | Password on Portal                                            |
    | PartTimeId             | Get from the url of the page you clock in/out                 |
    | AttendWork             | Job content                                                   |
    | DayofWeek_Clock        | Weekday you want to clock in/out, 0 is Monday and 6 is Sunday |
    | Random_delay_range     |The unit is minutes. This is the time the program will be delayed. Make you auto clock-in and clock-out more like human. |
 3.
    Set the script executable.
    ```
        $ sudo chmod 777 Auto_clock/clock_in.py
        $ sudo chmod 777 Auto_clock/clock_out.py
    ```

 4.
    Time calibration.

 5.
    Config the crontab.
    ```
        $ crontab -e

        # minute hour day month dayofweek COMMAND
        0 8 1-7 * * python3 /PATH/TO/Auto_clock/clock_in.py
        2 18 1-7 * * python3 /PATH/TO/Auto_clock/clock_out.py
        # For example, 50 hours per month.
    ```
