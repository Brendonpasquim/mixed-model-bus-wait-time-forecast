# mixed-model-bus-wait-time-forecast

## Author
Repository author can be contacted through the e-mail `brendonpasquim@alunos.utfpr.edu.br`

## Scope

This project implements a set of mixed models that forecast the wait time at bus stops in urban public transport.

## Considerations
- `main.Rmd` file is the entry point of the project. Mixed models are called M1, M2, M3 and M3+Sazonality and were developed incrementally.
- `input.csv` file shows the expected data input format;
- This was developed considering the Curitiba - Brazil data model provided by URBS/IPPUC. However, with minor adjustments it should easily fit other datasets.
- This source code is available to be reused and extended, but it is mandatory to give credits to the authors.
  - For academic researchers, it is possible to cite the related white paper:
``` latex
@inproceedings{courb,
 author = {Brendon Pasquim and Keiko Fonseca and Luiz Melo Jr.},
 title = {Quando chega? Análise de previsibilidade de tempos de espera em transporte público urbano utilizando Modelos Mistos},
 booktitle = {Anais do IX Workshop de Computação Urbana},
 location = {Natal/RN},
 year = {2025},
 keywords = {Previsão de tempo de espera, Modelos mistos, Transporte público urbano, Dados abertos},
 issn = {2595-2706},
 pages = {15--28},
 publisher = {SBC},
 address = {Porto Alegre, RS, Brasil},
 doi = {10.5753/courb.2025.7932},
 url = {https://sol.sbc.org.br/index.php/courb/article/view/35248}
}
```

## Pseudocode

```
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