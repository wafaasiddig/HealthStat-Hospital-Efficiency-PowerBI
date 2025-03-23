## Total Discharges
    Total Discharges = COUNTROWS(hospital_discharges)
 Counts the total number of hospital discharges in the dataset.


## Total Hospitals
    Total Hospitals = DISTINCTCOUNT(hospital_discharges[facility_id])
Counts the total number of distinct hospitals in the dataset.

## Total Surgeons
    Total Surgeons = DISTINCTCOUNT(hospital_discharges[operating_provider_id])
Counts the total number of distinct surgeons performing elective hip replacement surgeries.

## Average LOS Days
    Average LOS Days = AVERAGE(hospital_discharges[length_of_stay])
Calculates the average length of stay (LOS) for all patients across hospitals.

## Average LOS Days (Overall State Average)
    Average LOS Days_ALL = CALCULATE([Average LOS Days], ALL())
Calculates the overall state average length of stay (LOS), ignoring any filters.

## Average Cost per Discharge
    Average Cost per Discharge = DIVIDE(SUM(hospital_discharges[total_costs]), [Total Discharges])
Computes the average cost per discharge by dividing the total costs by the total number of discharges.

## Average Cost per Discharge (Overall State Average)
Average Cost per Discharge_ALL = CALCULATE([Average Cost per Discharge], ALL())
Calculates the overall state average cost per discharge, ignoring any filters.

## Percentage Variation in Average Cost per Discharge
    % Var Average Cost per Discharge =
    DIVIDE(
        ([Average Cost per Discharge] - [Average Cost per Discharge_ALL]),
        [Average Cost per Discharge_ALL]
    )
Calculates the percentage difference between a hospital's average cost per discharge and the overall state average.

## Percentage Variation in Average LOS Days
    % Var Average LOS Days =
    DIVIDE(
        ([Average LOS Days] - [Average LOS Days_ALL]),
        [Average LOS Days_ALL]
    )
Calculates the percentage difference between a hospital's average LOS and the overall state average.

## Surgical Program Size
    Surgical Program Size =
    SWITCH(
        TRUE(),
        [Total Discharges] <= 200, "0-199",
        [Total Discharges] <= 400, "200-399",
        [Total Discharges] <= 600, "400-599",
        "600+"
    )
Groups hospitals into categories based on their total discharges (e.g., 0-199, 200-399, etc.).

## Age Bins
    Age Bins =
    IF(
        OR(
            hospital_discharges[age_group] = "50 to 69",
            hospital_discharges[age_group] = "70 or Older"
        ),
        "Age 50+",
        "Age <50"
    )
Groups patients into two age categories: "Age 50+" and "Age <50".
