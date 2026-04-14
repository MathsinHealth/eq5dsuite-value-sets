# eq5dsuite-value-sets

Value set data for the [eq5dsuite](https://github.com/MathsInHealth/eq5dsuite) 
project. This repository provides country-specific EQ-5D value sets 
for the EQ-5D-3L, EQ-5D-5L, and EQ-5D-Y-3L instruments, used by 
the eq5dsuite tools to support automatic value set updates.

## Structure

```{r}
eq5dsuite-value-sets/
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