# point_lead_event_log

## Description

<details>
<summary><strong>Table Definition</strong></summary>

```sql
CREATE TABLE `point_lead_event_log` (
  `event_id` int(10) unsigned NOT NULL,
  `lead_id` bigint(20) unsigned NOT NULL,
  `ip_id` int(10) unsigned DEFAULT NULL,
  `date_fired` datetime NOT NULL,
  PRIMARY KEY (`event_id`,`lead_id`),
  KEY `IDX_C2A3BDBA71F7E88B` (`event_id`),
  KEY `IDX_C2A3BDBA55458D` (`lead_id`),
  KEY `IDX_C2A3BDBAA03F5E9F` (`ip_id`),
  CONSTRAINT `FK_C2A3BDBA55458D` FOREIGN KEY (`lead_id`) REFERENCES `leads` (`id`) ON DELETE CASCADE,
  CONSTRAINT `FK_C2A3BDBA71F7E88B` FOREIGN KEY (`event_id`) REFERENCES `point_trigger_events` (`id`) ON DELETE CASCADE,
  CONSTRAINT `FK_C2A3BDBAA03F5E9F` FOREIGN KEY (`ip_id`) REFERENCES `ip_addresses` (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci ROW_FORMAT=DYNAMIC
```

</details>

## Columns

| Name | Type | Default | Nullable | Children | Parents | Comment |
| ---- | ---- | ------- | -------- | -------- | ------- | ------- |
| event_id | int(10) unsigned |  | false |  | [point_trigger_events](point_trigger_events.md) |  |
| lead_id | bigint(20) unsigned |  | false |  | [leads](leads.md) |  |
| ip_id | int(10) unsigned | NULL | true |  | [ip_addresses](ip_addresses.md) |  |
| date_fired | datetime |  | false |  |  |  |

## Constraints

| Name | Type | Definition |
| ---- | ---- | ---------- |
| FK_C2A3BDBA55458D | FOREIGN KEY | FOREIGN KEY (lead_id) REFERENCES leads (id) |
| FK_C2A3BDBA71F7E88B | FOREIGN KEY | FOREIGN KEY (event_id) REFERENCES point_trigger_events (id) |
| FK_C2A3BDBAA03F5E9F | FOREIGN KEY | FOREIGN KEY (ip_id) REFERENCES ip_addresses (id) |
| PRIMARY | PRIMARY KEY | PRIMARY KEY (event_id, lead_id) |

## Indexes

| Name | Definition |
| ---- | ---------- |
| IDX_C2A3BDBA55458D | KEY IDX_C2A3BDBA55458D (lead_id) USING BTREE |
| IDX_C2A3BDBA71F7E88B | KEY IDX_C2A3BDBA71F7E88B (event_id) USING BTREE |
| IDX_C2A3BDBAA03F5E9F | KEY IDX_C2A3BDBAA03F5E9F (ip_id) USING BTREE |
| PRIMARY | PRIMARY KEY (event_id, lead_id) USING BTREE |

## Relations

![er](point_lead_event_log.svg)

---

> Generated by [tbls](https://github.com/k1LoW/tbls)
