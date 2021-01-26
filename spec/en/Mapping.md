## Data Mapping for Dwell Times

The components of TheTransitClock's dwell time model are mapped to tables and fields required in GTFS and GTFS-ride. 

## Feed Files

| Data standard|  Filename | Static passenger arrival rate | Stability vs. immediacy trade-off | Passenger alighting rates | Passenger activity dwell | Adherence dwell | Fixed dwell  |
|  ------ |  ------ | ------ | ------ |------ | ------ |------ | ------ |
| GTFS |  [agency.txt](https://github.com/TheTransitClock/GTFS/blob/master/gtfs/spec/en/reference.md#agencytxt)  |  |  |  |  |  |  |
| GTFS |  [stops.txt](https://github.com/TheTransitClock/GTFS/blob/master/gtfs/spec/en/reference.md#stopstxt)  |  |  |  |  |  |  |
| GTFS |  [routes.txt](https://github.com/TheTransitClock/GTFS/blob/master/gtfs/spec/en/reference.md#routestxt)  |  |  |  |  |  |  |
| GTFS |  [trips.txt](https://github.com/TheTransitClock/GTFS/blob/master/gtfs/spec/en/reference.md#tripstxt)   |  |  |  |  |  |  |
| GTFS |  [stop_times.txt](https://github.com/TheTransitClock/GTFS/blob/master/gtfs/spec/en/reference.md#stop_timestxt)   |  |  |  |  |✅   | ✅|  |
| GTFS |  [calendar.txt](https://github.com/TheTransitClock/GTFS/blob/master/gtfs/spec/en/reference.md#calendartxt)   |  |  |  |  |  |  |
| GTFS |  [calendar_dates.txt](https://github.com/TheTransitClock/GTFS/blob/master/gtfs/spec/en/reference.md#calendar_datestxt)  |  |  |  |  |  |  |
| GTFS |  [fare_attributes.txt](https://github.com/TheTransitClock/GTFS/blob/master/gtfs/spec/en/reference.md#fare_attributestxt)  |  |  |  |  |  |  |
| GTFS |  [fare_rules.txt](https://github.com/TheTransitClock/GTFS/blob/master/gtfs/spec/en/reference.md#fare_rulestxt)  |  |  |  |  |  |  |
| GTFS |  [shapes.txt](https://github.com/TheTransitClock/GTFS/blob/master/gtfs/spec/en/reference.md#shapestxt)  |  |  |  |  |  |  |
| GTFS |  [frequencies.txt](https://github.com/TheTransitClock/GTFS/blob/master/gtfs/spec/en/reference.md#frequenciestxt)  |  |  |  |  |  |  |
| GTFS |  [transfers.txt](https://github.com/TheTransitClock/GTFS/blob/master/gtfs/spec/en/reference.md#transferstxt)  |  |  |  |  |  |  |
| GTFS |  [feed_info.txt](https://github.com/TheTransitClock/GTFS/blob/master/gtfs/spec/en/reference.md#feed_infotxt)  |  |  |  |  |  |  |
| GTFS-ride |  [board_alight.txt](https://github.com/TheTransitClock/GTFS-ride/blob/master/spec/en/reference.md#board_alighttxt) | ✅  |  ✅ |  ✅ | |  ✅|  |
| GTFS-ride |  [trip_capacity.txt](https://github.com/TheTransitClock/GTFS-ride/blob/master/spec/en/reference.md#trip_capacitytxt) |  |  |  |  ✅ |    |
| GTFS-ride |  [rider_trip.txt](https://github.com/TheTransitClock/GTFS-ride/blob/master/spec/en/reference.md#rider_triptxt) |  |  |  |  |  |  |
| GTFS-ride |  [ridership.txt](https://github.com/TheTransitClock/GTFS-ride/blob/master/spec/en/reference.md#ridershiptxt) |  |  |  |  |  |  |
| GTFS-ride |  [ride_feed_info.txt](https://github.com/TheTransitClock/GTFS-ride/blob/master/spec/en/reference.md#ride_feed_infotxt) | ✅  |  ✅ |  ✅ | ✅ |  ✅|  

## Field Definitions

_Only files unique to dwell time modeling are mapped below. Definitions for the tables and fields can be found at [https://github.com/TheTransitClock/GTFS/blob/master/gtfs/spec/en/reference.md](https://github.com/TheTransitClock/GTFS/blob/master/gtfs/spec/en/reference.md) for GTFS and [https://github.com/TheTransitClock/GTFS-ride/blob/master/spec/en/reference.md](https://github.com/TheTransitClock/GTFS-ride/blob/master/spec/en/reference.md) for GTFS ride._

**Bolded** fields are unique to TheTransitClock's version of GTFS-ride and GTFS.


### *__stop_times.txt__*

File: **Required**

|  Field Name | Static passenger arrival rate | Stability vs. immediacy trade-off | Passenger alighting rates | Passenger activity dwell | Adherence dwell | Fixed dwell  |
|  ------ | ------ | ------ |------ | ------ |------ | ------ |
|  trip_id |  |  |  |  |✅   | ✅|  |
|  arrival_time   |  |  |  |  |✅   | ✅|  |
|  departure_time |  |  |  |  |✅   | ✅|  |
|  stop_id |  |  |  |  |✅   | ✅|  |
|  stop_sequence |  |  |  |  |✅   | ✅|  |
|  stop_headsign |  |  |  |  |  |  |
|  pickup_type |  |  |  |  |  |  |
|  drop_off_type |  |  |  |  |  |  |
|  continuous_pickup |  |  |  |  |  |  |
|  continuous_drop_off |  |  |  |  |  |  |
|  shape_dist_traveled |  |  |  |  |  |  |
|  timepoint |  |  |  |  |  |  |  |  |  |  |  |  |
|  **stop_service_time** |  |  |  |  |✅   | ✅|  |
|  **stop_zone_travel_time** |  |  |  |  |✅   | ✅|  |

### *__board_alight.txt__*

File: **Required**

|  Field Name | Static passenger arrival rate | Stability vs. immediacy trade-off | Passenger alighting rates | Passenger activity dwell | Adherence dwell | Fixed dwell  |
|  ------ | ------ | ------ |------ | ------ |------ | ------ |
| trip_id | ✅  |  ✅ |  ✅ | |  ✅|  |
| stop_id | ✅  |  ✅ |  ✅ | |  ✅|  |
| stop_sequence| ✅  |  ✅ |  ✅ | |  ✅|  |
| record_use | ✅  |  ✅ |  ✅ | |  ✅|  |
| schedule_relationship |  |  |  |  |  |  |
| boardings | ✅  |  ✅ |  ✅ |
| alightings | ✅  |  ✅ |  ✅ |
| current_load |  |  |  |  |  |  |
| load_count |  |  |✅  
| load_type |  |  |✅  
| rack_down | ✅  |  ✅ |  ✅ |
| bike_boardings |  |  |  |  |  |  |
| bike_alightings |  |  |  |  |  |  |
| ramp_used | ✅  |  ✅ |  ✅ |
| ramp_boardings |  |  |  |  |  |  |
| ramp_alightings |  |  |  |  |  |  |
| service_date | ✅  |  ✅ |  ✅ | |  ✅|  |
| service_arrival_time | ✅  |  ✅ |  ✅ | |  ✅|  |
| service_departure_time | ✅  |  ✅ |  ✅ | |  ✅|  |
| source |  |  |  |  |  |  |
| **direction_id** | ✅  |  ✅ |  ✅ | |  ✅|  |
| **service_door_opening_time** | ✅  |  ✅|| |  ✅|  |
| **service_door_closing_time** | ✅  |  ✅|| |  ✅|  |

### *__trip_capacity.txt__*

File: **Required**

|  Field Name | Static passenger arrival rate | Stability vs. immediacy trade-off | Passenger alighting rates | Passenger activity dwell | Adherence dwell | Fixed dwell  |
|  ------ | ------ | ------ |------ | ------ |------ | ------ |
| agency_id |  |  |  |  ✅ |    |
| trip_id |  |  |  |  ✅ |    |
| service_date |
| vehicle_description |  |  |  |  ✅ |    |
| seated_capacity |  |  |  |  ✅ |    |
| standing_capacity |  |  |  |  ✅ |    |
| wheelchair_capacity |  |  |  |  ✅ |    |
| bike_capacity |  |  |  |  ✅ |    |
| **time_per_boarding** |  |  |  |  ✅ |    |
| **time_per_alighting** |  |  |  |  ✅ |    |
| **time_per_ramp_deployment** |  |  |  |  ✅ |    |
| **time_per_rack_deployment** |  |  |  |  ✅ |    |

### *__ride_feed_info.txt__*

File: **Required**

|  Field Name | Static passenger arrival rate | Stability vs. immediacy trade-off | Passenger alighting rates | Passenger activity dwell | Adherence dwell | Fixed dwell  |
|  ------ | ------ | ------ |------ | ------ |------ | ------ |
| ride_files | ✅  |  ✅ |  ✅ | ✅ |  ✅|  
| ride_start_date | ✅  |  ✅ |  ✅ | ✅ |  ✅|  
| ride_end_date | ✅  |  ✅ |  ✅ | ✅ |  ✅|  
| gtfs_feed_date | ✅  |  ✅ |  ✅ | ✅ |  ✅|  
| default_currency_type |  |  |  |  |  |  |
| ride_feed_version | ✅  |  ✅ |  ✅ | ✅ |  ✅|  
