# Py Ledger Tools

Python based tools for manipulating accounting data for use with [ledger](ledger-cli.org)

See also: 

- [plaintextaccounting.org](plaintextaccounting.org)

- Ruby-based [ledger-tools](https://github.com/chrisnatali/ledger-tools) repo for a more complete set of tools

## Usage

The output of any of the `2ledger` commands should be usable with ledger
for register, balance reports

### qif2ledger

Use to migrate Quicken data to Ledger format

Steps:
- Export each quicken account as a QIF
- Run them through qif2ledger to create a ledger formatted file
- [optional] Find/replace categories with appropriate account names
  I use the prefixes suggested in the ledger-cli doc (Assets, Expenses, Liabilities, Income, Equity)

Example using sample QIF file provided:

```
> python qif2ledger.py -a Assets:Checking sample.qif
2005/06/19 Opening Balance
    Equity  $-3134.0
    Assets:checking

2005/06/19 My Am I University
    ;Discrete Math Dropped Reimb
    Education:Tuition  $3184.0
    Assets:checking

2005/06/19 Tech Software, LLC
    ;Parking in São Paulo
    Reimbursement:Work Expenses  $-175.0
    Assets:checking
```
 
## Testing

Run nosetests
