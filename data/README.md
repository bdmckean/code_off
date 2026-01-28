# Sample Transaction Data

This directory contains anonymized sample CSV files in various formats for testing the budget tracking applications.

## Files

### 1. simple_transactions.csv
**Format**: Basic 3-column format (Date, Amount, Description)
**Use Case**: Simplest format for quick testing
**Rows**: 14 transactions
**Columns**:
- `Date`: Transaction date (YYYY-MM-DD format)
- `Amount`: Transaction amount (positive values)
- `Description`: Brief description of the transaction

### 2. credit_card_transactions.csv
**Format**: Detailed credit card statement export
**Use Case**: Credit card processing with debit/credit columns
**Rows**: 15 transactions
**Columns**:
- `Transaction Date`: Date transaction occurred
- `Posted Date`: Date transaction posted to account
- `Card No.`: Card number (anonymized as xxxx)
- `Description`: Merchant/transaction description
- `Category`: Bank-provided category
- `Debit`: Debit amount (charges)
- `Credit`: Credit amount (payments/refunds)

### 3. chase_transactions.csv
**Format**: Chase bank export format
**Use Case**: Testing with Type field and Memo column
**Rows**: 13 transactions
**Columns**:
- `Card`: Card number (anonymized)
- `Transaction Date`: Date of transaction
- `Post Date`: Date posted to account
- `Description`: Transaction description
- `Category`: Transaction category
- `Type`: Transaction type (Sale, Payment, Adjustment, Fee)
- `Amount`: Transaction amount (negative for debits)
- `Memo`: Optional memo field

### 4. bank_checking_transactions.csv
**Format**: Bank checking account export
**Use Case**: Testing with Status field and Original Description
**Rows**: 15 transactions
**Columns**:
- `Date`: Transaction date
- `Description`: Cleaned description
- `Original Description`: Raw transaction description
- `Category`: Transaction category
- `Amount`: Transaction amount (negative for debits)
- `Status`: Transaction status (Posted, Pending)

## Anonymization

All files have been anonymized:
- Card numbers replaced with "xxxx"
- Merchant names genericized (e.g., "Grocery Store" instead of specific chain)
- Personal information removed
- Account numbers redacted
- Specific locations generalized

## Testing Both Applications

Both budget_claude (Flask) and budget_cursor (FastAPI) can process any of these formats. The applications will:
1. Auto-detect CSV format
2. Parse various column structures
3. Extract Date, Amount, and Description fields
4. Handle different date formats
5. Parse positive/negative amounts
6. Deal with extra columns gracefully

## Expected Behavior

### Validation
- `simple_transactions.csv`: Should pass all validation (clean format)
- `credit_card_transactions.csv`: Should handle Debit/Credit columns
- `chase_transactions.csv`: Should handle negative amounts and Type field
- `bank_checking_transactions.csv`: Should handle Status and dual description fields

### Categorization
The AI categorization feature should suggest appropriate categories:
- Grocery Store → Food & Groceries
- Streaming Service → Subscriptions or Entertainment
- Gas Station → Transportation
- Utility Bills → Utilities
- Restaurant → Food & Dining
- Insurance → Healthcare or Other
- etc.

## Integration Testing

Use these files to test:
1. File upload and parsing
2. CSV validation rules
3. AI categorization suggestions
4. Batch processing (5 transactions at once)
5. Manual categorization
6. Progress saving and resuming
7. Analytics generation
8. Export functionality

## Format Compatibility

| Format | budget_claude | budget_cursor | Notes |
|--------|--------------|--------------|-------|
| simple_transactions.csv | ✅ | ✅ | Easiest to parse |
| credit_card_transactions.csv | ✅ | ✅ | Handles Debit/Credit split |
| chase_transactions.csv | ✅ | ✅ | Type field adds context |
| bank_checking_transactions.csv | ✅ | ✅ | Dual descriptions useful |

## License

These are synthetic anonymized sample files for testing purposes only.
