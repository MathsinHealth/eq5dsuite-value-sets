# eq5dsuite-value-sets

Value set data for the [eq5dsuite](https://github.com/MathsInHealth/eq5dsuite) 
project. This repository provides country-specific EQ-5D value sets 
for the EQ-5D-3L, EQ-5D-5L, and EQ-5D-Y-3L instruments, used by 
the eq5dsuite tools to support automatic value set updates.

## Structure

```{r}
eq5dsuite-value-sets/
├── migrations.csv         # Historical value set renames
├── EQ-5D-3L/
│   ├── value_sets.csv     # Index of all available 3L value sets
│   └── [VS_code].csv      # One file per value set
├── EQ-5D-5L/
│   ├── value_sets.csv     # Index of all available 5L value sets
│   └── [VS_code].csv      # One file per value set
└── EQ-5D-Y-3L/
├── value_sets.csv     # Index of all available Y-3L value sets
└── [VS_code].csv      # One file per value set
```

## File formats

### migrations.csv
Records all historical value set renames. This file is read by
the eq5dsuite R package to automatically rename installed value
sets when there are several value sets available for a country.
The original code needs to be disambiguated with a year/method suffix.

| Column | Description |
|---|---|
| version | Instrument version (3L, 5L, Y3L) |
| old_VS_code | The original VS_code being renamed |
| new_VS_code | The new VS_code to use |
| reason | Brief explanation of why the rename was needed |
| date | Date the migration was added (YYYY-MM-DD) |

**When to add a migration row:**
- A second value set is published for a country that already
  has one (e.g. Netherlands publishes a 2026 set when the code NL already exists
  refering to the value set published in 2006)
- A VS_code needs to be corrected for clarity (e.g. adding a
  method suffix like _TTO or _VAS)

**Important:** never delete rows from migrations.csv. Rows are
used to track which renames have already been applied to each
user's installation.

### value_sets.csv
Index file listing all available value sets for each instrument:

| Column | Description |
|---|---|
| Version | Instrument version (3L, 5L, Y3L) |
| Name | Full name of the value set |
| Name_short | Short name |
| Country_code | ISO country code |
| VS_code | Unique identifier used as filename |
| doi | DOI of the source publication |
| citation | citation of the source publication |

### [VS_code].csv
Individual value set file with two columns:

| Column | Description |
|---|---|
| state | EQ-5D health state code |
| value | Utility value for that health state |

## Usage

These files are accessed automatically by the eq5dsuite tools.
They can also be downloaded and used directly.

## Contributing

To add a new value set, please open an issue or submit a pull 
request with:
- The new value set CSV file named after its VS_code
- An updated value_sets.csv index entry

## Contact

[info@mathsinhealth.com](mailto:info@mathsinhealth.com)

## License

MIT License. See [LICENSE](LICENSE) for details.