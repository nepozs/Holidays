[![hacs_badge](https://img.shields.io/badge/HACS-Default-orange.svg)](https://github.com/custom-components/hacs) [![Holidays](https://img.shields.io/github/v/release/bruxy70/Holidays.svg?1)](https://github.com/bruxy70/Holidays) ![Maintenance](https://img.shields.io/maintenance/yes/2022.svg)

[![Buy me a coffee](https://img.shields.io/static/v1.svg?label=Buy%20me%20a%20coffee&message=🥨&color=black&logo=buy%20me%20a%20coffee&logoColor=white&labelColor=6f4e37)](https://www.buymeacoffee.com/3nXx0bJDP)

{% if prerelease %}
### NB!: This is a Beta version!
{% endif %}

# Holidays
The `holidays` componnent is a **Home Assistant** integration that creates `calendar` entities with a list of public holidays in a country, based on the Python (Holidays)[https://github.com/dr-prodigy/python-holidays] library.
It's primary purpose is to work with `garbage_collection` integration to automatically move entities with `manual_update` automation blueprints. But it can also be used independently to show next public holiday in given country (or multiple countries).

## Parameters
|Parameter |Required|Description
|:----------|----------|------------
| `country` | Yes | Country holidays - the country code (see [holidays](https://github.com/dr-prodigy/python-holidays) for the list of valid country codes).<br/>*Example:* `US` 
| `holiday_pop_named` | No | Ignore holidays (list of holiday names) *Example:* `"Columbus Day"`, `"Veterans Day"`
| `prov` | No | Province (see [holidays](https://github.com/dr-prodigy/python-holidays) ).
| `state` | No | State (see [holidays](https://github.com/dr-prodigy/python-holidays) ).
| `observed` | No | Observed (see [holidays](https://github.com/dr-prodigy/python-holidays) ).

## State and Attributes
### `state`
The State contains the number of days to the next country holiday. It is `0` if today is a public holiday.

### Attributes
| Attribute | Description
|:----------|------------
| `next_date` | The date of holiday
| `holidays` | List of used country (last year, this year and next year). This is used by the `garbage_collection` blueprints to offset collections if they fall on a public holiday (or if holiday was earlier on in the week)

Check the <a href="https://github.com/bruxy70/Holidays">repository</a> for installation instructions.