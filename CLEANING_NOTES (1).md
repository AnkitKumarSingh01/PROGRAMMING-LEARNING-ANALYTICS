# DSA Phase 2 Cleaning Notes

## Source
`java_submissions.csv` from the downloaded DSA Dataset.

## Rules applied
1. The original raw dataset is not modified.
2. No rows were deleted because there are zero exact duplicate rows.
3. `result` is normalized into `result_type` with three observed categories: `success`, `fail`, and `empty`.
4. Boolean indicators `is_success`, `is_failure`, and `is_empty` are derived from `result_type`.
5. Unix-millisecond timestamps are converted to UTC datetimes.
6. Rows with missing timestamps are retained for submission/outcome metrics, but excluded from time-derived metrics such as active days and practice gaps.
7. The highly incomplete `timisOrderedmp` and `timismp` fields are not used in the primary analysis.
8. Student-level metrics are derived without inventing scores.

## Important methodological note
`success_rate_all_submissions_pct` treats `empty` as a non-success in the denominator. `success_rate_evaluated_pct` excludes `empty` from the denominator. We will compare these definitions during validation before selecting the primary performance metric.
