# PrayerTimeScheduler

A Python project to fetch Islamic prayer times for any city using the [Aladhan API](https://aladhan.com/prayer-times-api), convert them into CSV format, and generate an ICS calendar with reminders for each prayer.

## Features
- Fetch prayer times for any city using the Aladhan API.
- Convert prayer times into a CSV file.
- Create an ICS file with prayer time events and reminders for Imam Jama'ah (in 10 minutes).
- Easy-to-use and highly customizable.

## Setup & Installation

To get started with this project, follow these steps:

### Prerequisites

Additionally, you will need to install the required dependencies. You can do this by running:


pip install requests

## Usage
Clone this repository to your local machine: or open using colab


git clone https://github.com/omarShiraz/PrayerTimeScheduler.git
cd PrayerTimeScheduler
In the script main.py, replace the city and country values with your desired location.

Run the script to fetch prayer times for the specified year and city or longitude and latitude refer for further details on the API
https://aladhan.com/prayer-times-api#tag/Monthly-Annual-Prayer-Times-Calendar/paths/~1v1~1calendarByCity~1%7Byear%7D~1%7Bmonth%7D/get

A prayer_times.csv file containing the prayer times for each day of the specified year.
An prayer_times.ics file that contains the events and alarms for the prayer times.
Configuration
You can customize the script's behavior by editing the following variables:

city: The name of the city for which you want to fetch prayer times.
country: The country code (ISO 3166-1 alpha-2) of the city.
For example:

python
Copy code
city = "Colombo"
country = "LK"  # Sri Lanka (ISO Code)
Aladhan API Parameters
The Aladhan API supports several parameters that allow you to customize the prayer times:

city: The name of the city (e.g., "Colombo").
country: The country code (e.g., "LK" for Sri Lanka).
method: The calculation method to use (you can find a list of methods here).
month: Month for the prayer times (1-12).
year: Year for the prayer times.
For more details on the parameters, visit the Aladhan API Documentation.

## Example API Request
If you want to fetch prayer times for Colombo, Sri Lanka for the year 2025 using the Muslim World League method (method=2), you would call the API like this:

Change these values to get the exact prayer time for your region and method of calculation can be change below by chnaging the number

0 - Jafari / Shia Ithna-Ashari
1 - University of Islamic Sciences, Karachi
2 - Islamic Society of North America
3 - Muslim World League
4 - Umm Al-Qura University, Makkah
5 - Egyptian General Authority of Survey
7 - Institute of Geophysics, University of Tehran
8 - Gulf Region
9 - Kuwait
10 - Qatar
12 - Majlis Ugama Islam Singapura, Singapore
12 - Union Organization islamic de France
13 - Diyanet İşleri Başkanlığı, Turkey
14 - Spiritual Administration of Muslims of Russia
15 - Moonsighting Committee Worldwide (also requires shafaq parameter)
16 - Dubai (experimental)
17 - Jabatan Kemajuan Islam Malaysia (JAKIM)
18 - Tunisia
19 - Algeria
20 - KEMENAG - Kementerian Agama Republik Indonesia
21 - Morocco
22 - Comunidade Islamica de Lisboa
23 - Ministry of Awqaf, Islamic Affairs and Holy Places, Jordan
99 - Custom. See https://aladhan.com/calculation-methods


python
Copy code
params = {
    "city": "Colombo",
    "country": "LK",
    "method": 2,
    "year": 2025
}
## ICS Calendar
The generated .ics file contains prayer events for each day, with reminders set 10 minutes before the prayer time for the Imam Jama'ah. This can be added to any calendar that supports the iCalendar format (e.g., Google Calendar, Outlook).

## Example ICS Event
Here’s an example of how a prayer event will look in the ICS file:

ics
Copy code
BEGIN:VEVENT
SUMMARY:Fajr Prayer
DTSTART:20250101T05300000
DESCRIPTION:Imam Jama'ah for Fajr will be in 10 minutes at 5:40 AM
BEGIN:VALARM
ACTION:DISPLAY
DESCRIPTION:Reminder for Fajr Prayer
TRIGGER:-PT0M
END:VALARM
END:VEVENT
Each prayer time is represented as an event in the calendar with a reminder exactly at prayer time.

# Contributing
If you would like to contribute to this project, feel free to fork the repository, make your changes, and submit a pull request. Contributions are welcome!

# License
This project is licensed under the MIT License - see the LICENSE file for details.

