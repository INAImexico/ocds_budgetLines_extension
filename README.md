# Budget lines

## Background

There are multiple efforts in Mexico to implement the Open Contracting Data Standard (OCDS) through the whole contracting processes that are done in the country. The diversity of agencies related to this theme has caused the emergence of the Open Contracting Alliance in Mexico (ACA, by its inicials in spanish) who is in charge for the definition of the well-known "MX extensions".

The effort to define a package of extensions in Mexico (the MX extensions) is based on the need to match the transparency obligations, related to procurement processes, and the OCDS. This would lead to facilitate the implementation of the OCDS at local level without substantially increase the obligations to process and publish the data and documents of the public contracting procedures.

In the aim of mixing the OCDS with the Open Fiscal Data Package (OFDP), the Ministry of Finance (SHCP) has developed an extension who "allows users to express monetary figures in different types of budget classifications". As they wrote, with the `budgetClassifications` extension they "are currently using [...]: Economic, Administrative and the Funding Source [classifications], the OFDP standard is comprehensive enough to include more classifications depending on the country. Besides, this extension would also allow users to express amounts through their different accruing moments."

Nevertheless, at INAI we are proposing another composition for this extension and, in order to clarify and distinguish from the another, we named it `budgetLines`.

This composition allows you to express all the components of the identifier of the budget line. In Mexico, we have four main categories that each include multiple components.

**Administrative** | **Programmatic** | **Economic** | **Geographic** 
--|--|--|--
Branch, Responsible unit | Finality, Function, Sub function, Institutional activity, Budget program | Spending object, Spending type, Financial source | Region 

Thus, we propose the following structure:

## Example

```json
"budgetLines": [
  {
    "components": [
      {
        "name": "branch",
        "level": 1,
        "code": 12,
        "decription": "Health"
      },
      {
        "name": "resposibleUnit",
        "level": 2,
        "code": 310,
        "decription": "Management unit"
      }
    ],
    "measures": [
      {
        "id": "approved",
        "value": {
          "amount": 350000,
          "currency": "MXN"
        }
      }
    ]
  }
]
```
