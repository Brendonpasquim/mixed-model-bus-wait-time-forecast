# mixed-model-bus-wait-time-forecast

## Scope

This project implements a set of mixed models that forecast the wait time at bus stops in urban public transport.

## Considerations
- `main.Rmd` file is the entry point of the project. Mixed models are called M1, M2, M3 and M3+Sazonality and were developed incrementally.
- `input.csv` file shows the expected data input format;
- This was developed considering the Curitiba - Brazil data model provided by URBS/IPPUC. However, with minor adjustments it should easily fit other datasets.
- This source code is available to be reused and extended, but it is mandatory to give credits to the authors.
  - For academic researchers, it is possible to cite the related white paper.

## Pseudocode

``` json
Calculate_Wait_Times(Vehicle_ID, Itinerary_ID, data)
  // Input: Bus identifier
  // Input: Itinerary identifier
  // Input: Public Transport dataset
  // Output: HTML file

  If vehicles and itineraries in "data" do not match "Vehicle_ID" and "Itinerary_ID"
    Remove from dataset

  Repeat
    If vehicle sequence number "i" is less than the last bus stop "n" in the itinerary
      Calculate the time difference "t(i+1)-t(i)"

  Given "Itinerary_ID"
    Plot the wait time for all bus stops

  Given "data", calculate an Mixed Model
    Name the Fixed effect as "M1"
    Name the Random effect as "M2"
    Plot graphs for "M1" and "M2"
    Plot graphs related to "M2" residuals

  Given "data", calculate a Mixed Model considering autocorrelation in the residuals
    Name the model as "M3"
    Plot graphs for "M3"

  Given "data" AND the "M3" model
    Include a sazonality element to the model residuals
    Run validation tests on the residuals
    Plot graphs related to "M3" residuals

  Export results as HTML
```