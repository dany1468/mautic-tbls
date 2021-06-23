# leads

## Description

<details>
<summary><strong>Table Definition</strong></summary>

```sql
CREATE TABLE `leads` (
  `id` bigint(20) unsigned NOT NULL AUTO_INCREMENT,
  `owner_id` int(10) unsigned DEFAULT NULL,
  `stage_id` int(10) unsigned DEFAULT NULL,
  `is_published` tinyint(1) NOT NULL,
  `date_added` datetime DEFAULT NULL,
  `created_by` int(11) DEFAULT NULL,
  `created_by_user` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `date_modified` datetime DEFAULT NULL,
  `modified_by` int(11) DEFAULT NULL,
  `modified_by_user` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `checked_out` datetime DEFAULT NULL,
  `checked_out_by` int(11) DEFAULT NULL,
  `checked_out_by_user` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `points` int(11) NOT NULL,
  `last_active` datetime DEFAULT NULL,
  `internal` longtext COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT '(DC2Type:array)',
  `social_cache` longtext COLLATE utf8mb4_unicode_ci DEFAULT NULL COMMENT '(DC2Type:array)',
  `date_identified` datetime DEFAULT NULL,
  `preferred_profile_image` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `title` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `firstname` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `lastname` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `company` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `position` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `email` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `phone` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `mobile` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `address1` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `address2` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `city` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `state` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `zipcode` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `timezone` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `country` varchar(191) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `fax` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `preferred_locale` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `attribution_date` datetime DEFAULT NULL,
  `attribution` double DEFAULT NULL,
  `website` longtext COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `facebook` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `foursquare` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `instagram` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `linkedin` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `skype` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `twitter` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `IDX_179045527E3C61F9` (`owner_id`),
  KEY `IDX_179045522298D193` (`stage_id`),
  KEY `lead_date_added` (`date_added`),
  KEY `date_identified` (`date_identified`),
  KEY `title_search` (`title`),
  KEY `firstname_search` (`firstname`),
  KEY `lastname_search` (`lastname`),
  KEY `company_search` (`company`),
  KEY `position_search` (`position`),
  KEY `email_search` (`email`),
  KEY `mobile_search` (`mobile`),
  KEY `phone_search` (`phone`),
  KEY `points_search` (`points`),
  KEY `fax_search` (`fax`),
  KEY `address1_search` (`address1`),
  KEY `address2_search` (`address2`),
  KEY `city_search` (`city`),
  KEY `state_search` (`state`),
  KEY `zipcode_search` (`zipcode`),
  KEY `country_search` (`country`),
  KEY `preferred_locale_search` (`preferred_locale`),
  KEY `timezone_search` (`timezone`),
  KEY `last_active_search` (`last_active`),
  KEY `attribution_date_search` (`attribution_date`),
  KEY `attribution_search` (`attribution`),
  KEY `facebook_search` (`facebook`),
  KEY `foursquare_search` (`foursquare`),
  KEY `instagram_search` (`instagram`),
  KEY `linkedin_search` (`linkedin`),
  KEY `skype_search` (`skype`),
  KEY `twitter_search` (`twitter`),
  KEY `contact_attribution` (`attribution`,`attribution_date`),
  KEY `date_added_country_index` (`date_added`,`country`),
  CONSTRAINT `FK_179045522298D193` FOREIGN KEY (`stage_id`) REFERENCES `stages` (`id`) ON DELETE SET NULL,
  CONSTRAINT `FK_179045527E3C61F9` FOREIGN KEY (`owner_id`) REFERENCES `users` (`id`) ON DELETE SET NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci ROW_FORMAT=DYNAMIC
```

</details>

## Columns

| Name | Type | Default | Nullable | Extra Definition | Children | Parents | Comment |
| ---- | ---- | ------- | -------- | --------------- | -------- | ------- | ------- |
| id | bigint(20) unsigned |  | false | auto_increment | [asset_downloads](asset_downloads.md) [campaign_leads](campaign_leads.md) [campaign_lead_event_log](campaign_lead_event_log.md) [companies_leads](companies_leads.md) [contact_merge_records](contact_merge_records.md) [dynamic_content_lead_data](dynamic_content_lead_data.md) [dynamic_content_stats](dynamic_content_stats.md) [email_stats](email_stats.md) [focus_stats](focus_stats.md) [form_submissions](form_submissions.md) [lead_categories](lead_categories.md) [lead_companies_change_log](lead_companies_change_log.md) [lead_devices](lead_devices.md) [lead_donotcontact](lead_donotcontact.md) [lead_event_log](lead_event_log.md) [lead_frequencyrules](lead_frequencyrules.md) [lead_ips_xref](lead_ips_xref.md) [lead_lists_leads](lead_lists_leads.md) [lead_notes](lead_notes.md) [lead_points_change_log](lead_points_change_log.md) [lead_stages_change_log](lead_stages_change_log.md) [lead_tags_xref](lead_tags_xref.md) [lead_utmtags](lead_utmtags.md) [message_queue](message_queue.md) [monitoring_leads](monitoring_leads.md) [page_hits](page_hits.md) [plugin_citrix_events](plugin_citrix_events.md) [point_lead_action_log](point_lead_action_log.md) [point_lead_event_log](point_lead_event_log.md) [push_ids](push_ids.md) [push_notification_stats](push_notification_stats.md) [sms_message_stats](sms_message_stats.md) [stage_lead_action_log](stage_lead_action_log.md) [tweet_stats](tweet_stats.md) [video_hits](video_hits.md) |  |  |
| owner_id | int(10) unsigned | NULL | true |  |  | [users](users.md) |  |
| stage_id | int(10) unsigned | NULL | true |  |  | [stages](stages.md) |  |
| is_published | tinyint(1) |  | false |  |  |  |  |
| date_added | datetime | NULL | true |  |  |  |  |
| created_by | int(11) | NULL | true |  |  |  |  |
| created_by_user | varchar(191) | NULL | true |  |  |  |  |
| date_modified | datetime | NULL | true |  |  |  |  |
| modified_by | int(11) | NULL | true |  |  |  |  |
| modified_by_user | varchar(191) | NULL | true |  |  |  |  |
| checked_out | datetime | NULL | true |  |  |  |  |
| checked_out_by | int(11) | NULL | true |  |  |  |  |
| checked_out_by_user | varchar(191) | NULL | true |  |  |  |  |
| points | int(11) |  | false |  |  |  |  |
| last_active | datetime | NULL | true |  |  |  |  |
| internal | longtext | NULL | true |  |  |  | (DC2Type:array) |
| social_cache | longtext | NULL | true |  |  |  | (DC2Type:array) |
| date_identified | datetime | NULL | true |  |  |  |  |
| preferred_profile_image | varchar(191) | NULL | true |  |  |  |  |
| title | varchar(191) | NULL | true |  |  |  |  |
| firstname | varchar(191) | NULL | true |  |  |  |  |
| lastname | varchar(191) | NULL | true |  |  |  |  |
| company | varchar(191) | NULL | true |  |  |  |  |
| position | varchar(191) | NULL | true |  |  |  |  |
| email | varchar(191) | NULL | true |  |  |  |  |
| phone | varchar(191) | NULL | true |  |  |  |  |
| mobile | varchar(191) | NULL | true |  |  |  |  |
| address1 | varchar(191) | NULL | true |  |  |  |  |
| address2 | varchar(191) | NULL | true |  |  |  |  |
| city | varchar(191) | NULL | true |  |  |  |  |
| state | varchar(191) | NULL | true |  |  |  |  |
| zipcode | varchar(191) | NULL | true |  |  |  |  |
| timezone | varchar(191) | NULL | true |  |  |  |  |
| country | varchar(191) | NULL | true |  |  |  |  |
| fax | varchar(255) | NULL | true |  |  |  |  |
| preferred_locale | varchar(255) | NULL | true |  |  |  |  |
| attribution_date | datetime | NULL | true |  |  |  |  |
| attribution | double | NULL | true |  |  |  |  |
| website | longtext | NULL | true |  |  |  |  |
| facebook | varchar(255) | NULL | true |  |  |  |  |
| foursquare | varchar(255) | NULL | true |  |  |  |  |
| instagram | varchar(255) | NULL | true |  |  |  |  |
| linkedin | varchar(255) | NULL | true |  |  |  |  |
| skype | varchar(255) | NULL | true |  |  |  |  |
| twitter | varchar(255) | NULL | true |  |  |  |  |

## Constraints

| Name | Type | Definition |
| ---- | ---- | ---------- |
| FK_179045522298D193 | FOREIGN KEY | FOREIGN KEY (stage_id) REFERENCES stages (id) |
| FK_179045527E3C61F9 | FOREIGN KEY | FOREIGN KEY (owner_id) REFERENCES users (id) |
| PRIMARY | PRIMARY KEY | PRIMARY KEY (id) |

## Indexes

| Name | Definition |
| ---- | ---------- |
| address1_search | KEY address1_search (address1) USING BTREE |
| address2_search | KEY address2_search (address2) USING BTREE |
| attribution_date_search | KEY attribution_date_search (attribution_date) USING BTREE |
| attribution_search | KEY attribution_search (attribution) USING BTREE |
| city_search | KEY city_search (city) USING BTREE |
| company_search | KEY company_search (company) USING BTREE |
| contact_attribution | KEY contact_attribution (attribution, attribution_date) USING BTREE |
| country_search | KEY country_search (country) USING BTREE |
| date_added_country_index | KEY date_added_country_index (date_added, country) USING BTREE |
| date_identified | KEY date_identified (date_identified) USING BTREE |
| email_search | KEY email_search (email) USING BTREE |
| facebook_search | KEY facebook_search (facebook) USING BTREE |
| fax_search | KEY fax_search (fax) USING BTREE |
| firstname_search | KEY firstname_search (firstname) USING BTREE |
| foursquare_search | KEY foursquare_search (foursquare) USING BTREE |
| IDX_179045522298D193 | KEY IDX_179045522298D193 (stage_id) USING BTREE |
| IDX_179045527E3C61F9 | KEY IDX_179045527E3C61F9 (owner_id) USING BTREE |
| instagram_search | KEY instagram_search (instagram) USING BTREE |
| lastname_search | KEY lastname_search (lastname) USING BTREE |
| last_active_search | KEY last_active_search (last_active) USING BTREE |
| lead_date_added | KEY lead_date_added (date_added) USING BTREE |
| linkedin_search | KEY linkedin_search (linkedin) USING BTREE |
| mobile_search | KEY mobile_search (mobile) USING BTREE |
| phone_search | KEY phone_search (phone) USING BTREE |
| points_search | KEY points_search (points) USING BTREE |
| position_search | KEY position_search (position) USING BTREE |
| preferred_locale_search | KEY preferred_locale_search (preferred_locale) USING BTREE |
| skype_search | KEY skype_search (skype) USING BTREE |
| state_search | KEY state_search (state) USING BTREE |
| timezone_search | KEY timezone_search (timezone) USING BTREE |
| title_search | KEY title_search (title) USING BTREE |
| twitter_search | KEY twitter_search (twitter) USING BTREE |
| zipcode_search | KEY zipcode_search (zipcode) USING BTREE |
| PRIMARY | PRIMARY KEY (id) USING BTREE |

## Relations

![er](leads.svg)

---

> Generated by [tbls](https://github.com/k1LoW/tbls)
