# 01 — Authentication Log Analysis

## Objective

Practise using Splunk Search Processing Language (SPL) to review authentication activity and distinguish successful logons from failed attempts.

## Dataset Fields

The practice dataset will use the following fields:

| Field | Description |
|---|---|
| `user` | Account involved |
| `action` | Authentication result |
| `src_ip` | Source IP address |
| `device` | Device involved |

*Note: These are the expected practice fields. Queries and findings will be validated against the actual dataset before conclusions are recorded.*

## Investigation Exercises

### 1. Filter by user

```spl
user="alice"
```

### 2. Find failed logons

```spl
action="failure"
```

### 3. Combine conditions with AND

```spl
user="alice" action="failure"
```

### 4. Combine conditions with OR

```spl
action="success" OR action="failure"
```

### 5. Filter by user and multiple source IPs

```spl
user="bob" (src_ip="10.0.0.8" OR src_ip="10.0.0.9")
```

### 6. Display selected fields

```spl
user="alice" action="failure"
| table user action src_ip device
```

## Investigation Questions

- Which accounts generated failed authentication events?
- Which source IP addresses were involved?
- Were there repeated authentication failures?
- Is there any activity that requires further investigation?

## Findings

To be completed after executing the searches against the practice dataset.

## Conclusion

To be determined from the observed evidence.

---

*Understand → Investigate → Decide → Document.*
