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

However, at INAI through the Institutional Performance Evaluation System (SEDI) we can link the budget line with the specific activity of the unit that justify the need for the good or service.

**Administrative** | **Programmatic** | **Economic** | **Geographic** 
--|--|--|--
Branch, Responsible unit | Finality, Function, Sub function, Institutional activity, Budget program, *Strategic objective*, *Requesting unit*, *Specific activity* | Spending object, Spending type, Financial source | Region

*Italics* for the new components from INAI.

Thus, we propose the following structure:

## Example

```json
"budgetLines": [
  {
    "components": [
      {
        "name": "branch",
        "level": 1,
        "code": "44",
        "decription": "National Institute for Transparency, Access to Information and Personal Data Protection"
      },
      {
        "name": "resposibleUnit",
        "level": 2,
        "code": "210",
        "decription": "Management unit"
      },
      {
        "name": "finality",
        "level": 3,
        "code": "1",
        "decription": "Government"
      },
      {
        "name": "function",
        "level": 4,
        "code": "310",
        "decription": "Other general services"
      },
      {
        "name": "subFunction",
        "level": 5,
        "code": "04",
        "decription": "Access to public information"
      },
      {
        "name": "institutionalActivity",
        "level": 6,
        "code": "010",
        "decription": "Transparency, Access to Information and Personal Data Protection"
      },
      {
        "name": "budgetProgram",
        "level": 7,
        "code": "E001",
        "decription": "Guarantee the optimal fulfillment of the rights of access to information and personal data protection"
      },
      {
        "name": "strategicObjective",
        "level": 8,
        "code": "OE1",
        "decription": "Guarantee the optimal fulfillment of the rights of access to information and personal data protection"
      },
      {
        "name": "requestingUnit",
        "level": 9,
        "code": "230",
        "decription": "Information Technology Unit"
      },
      {
        "name": "specificActivity",
        "level": 10,
        "code": "GOA12",
        "decription": "Provision of integral services in the field of ICT"
      },
      {
        "name": "spendingObject",
        "level": 11,
        "code": "31904",
        "decription": "Computing infrastructure services"
      }
      {
        "name": "spendingType",
        "level": 12,
        "code": "1",
        "decription": "Current expenditure"
      }
      {
        "name": "budgetSource",
        "level": 13,
        "code": "1",
        "decription": "Fiscal resourses"
      }
      {
        "name": "region",
        "level": 14,
        "code": "09",
        "decription": "Mexico City"
      }
    ],
    "measures": [
      {
        "id": "approved",
        "value": {
          "amount": 35000,
          "currency": "MXN"
        }
      }
    ]
  }
]
```
As a result, we have the budget line identifier for this contracting process: "Electronic platform for distance training"

-------->  **44210131004010E001OE1230GOA12319041109**
