# GHL Custom Fields

## Master account (Loren AI sales)

| Field | Type | Used by |
|---|---|---|
| operator_company_name | text | demo form |
| operator_owner_name | text | demo form |
| fleet_size | number | demo form (used by ROI calc) |
| current_calls_per_day | number | demo form |
| current_missed_call_rate | percent | demo form |
| current_dispatcher_count | number | demo form |
| biggest_challenge | dropdown | demo form |
| broker_mix | multi-select | demo form (MTM/Modivcare/Verida/Access2Care/SafeRide/Private) |
| roi_recovered_revenue_annual | number | calculated post-form |
| roi_payroll_savings_monthly | number | calculated post-form |
| persona_inferred | dropdown | auto-tagged (Otis/Olivia/Eric/Unknown) |
| tier_quoted | dropdown | manual (Founder/Growth/Fleet) |
| stripe_customer_id | text | auto on close |
| go_live_date | date | manual on onboarding |
| client_subdomain | text | auto on subdomain creation |

## Per-client sub-account (operations)

| Field | Type | Notes |
|---|---|---|
| patient_first_name | text | |
| patient_last_name | text | |
| patient_dob | date | for broker validation |
| medicaid_id | text | encrypted |
| broker_name | dropdown | MTM / Modivcare / etc. |
| broker_auth_number | text | per-trip |
| pickup_address | address | |
| dropoff_address | address | |
| pickup_datetime | datetime | |
| mobility_type | dropdown | ambulatory / wheelchair / stretcher / bariatric |
| special_accommodations | text | (oxygen, escort, behavioral support) |
| facility_account_id | reference | links to facility contact |
| ride_status | dropdown | booked / en-route / completed / no-show / cancelled |
| assigned_driver_id | reference | links to driver |
| assigned_vehicle_id | reference | links to vehicle |
| nps_score | number 1–5 | |
| nps_response_text | text | |
| no_show_recovery_attempted | bool | |
| no_show_recovery_rebooked | bool | |
