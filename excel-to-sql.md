# Excel → SQL / pandas Cheat Sheet

## The Big 10 Translations

| Excel | SQL | pandas |
|-------|-----|--------|
| Filter rows (AutoFilter) | `WHERE column = 'value'` | `df[df['column'] == 'value']` |
| VLOOKUP | `JOIN` | `df.merge()` |
| SUMIFS | `SUM() ... WHERE` / `GROUP BY` | `df.groupby().sum()` |
| COUNTIFS | `COUNT() ... WHERE` / `GROUP BY` | `df.groupby().count()` |
| Pivot Table | `GROUP BY` + aggregate | `df.pivot_table()` |
| IF formula | `CASE WHEN ... THEN ... ELSE ... END` | `df['col'].apply()` / `np.where()` |
| Remove duplicates | `SELECT DISTINCT` | `df.drop_duplicates()` |
| Sort (A→Z) | `ORDER BY column ASC` | `df.sort_values()` |
| Average | `AVG(column)` | `df['column'].mean()` |
| Text join (&) | `CONCAT(col1, col2)` | `df['col1'] + df['col2']` |

## Key mindset shift
- Excel thinks in **cells** — you point at B2, drag formulas
- SQL thinks in **sets** — you describe what you want from a whole table
- pandas thinks in **columns** — you operate on entire columns at once