
# Team Object

*This model accepts additional fields of type Object.*

## Structure

`TeamObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Archived` | `Boolean` | Optional | - | Boolean getArchived() | setArchived(Boolean archived) |
| `AvatarBaseUrl` | `String` | Optional | - | String getAvatarBaseUrl() | setAvatarBaseUrl(String avatarBaseUrl) |
| `Created` | `Integer` | Optional | - | Integer getCreated() | setCreated(Integer created) |
| `DateCreate` | `Integer` | Optional | - | Integer getDateCreate() | setDateCreate(Integer dateCreate) |
| `Deleted` | `Boolean` | Optional | - | Boolean getDeleted() | setDeleted(Boolean deleted) |
| `Description` | `String` | Optional | - | String getDescription() | setDescription(String description) |
| `Discoverable` | `Object` | Optional | - | Object getDiscoverable() | setDiscoverable(Object discoverable) |
| `Domain` | `String` | Required | - | String getDomain() | setDomain(String domain) |
| `EmailDomain` | `String` | Required | - | String getEmailDomain() | setEmailDomain(String emailDomain) |
| `EnterpriseId` | `String` | Optional | **Constraints**: *Pattern*: `^[E][A-Z0-9]{8,}$` | String getEnterpriseId() | setEnterpriseId(String enterpriseId) |
| `EnterpriseName` | `String` | Optional | - | String getEnterpriseName() | setEnterpriseName(String enterpriseName) |
| `ExternalOrgMigrations` | [`ExternalOrgMigrations`](../../doc/models/external-org-migrations.md) | Optional | - | ExternalOrgMigrations getExternalOrgMigrations() | setExternalOrgMigrations(ExternalOrgMigrations externalOrgMigrations) |
| `HasComplianceExport` | `Boolean` | Optional | - | Boolean getHasComplianceExport() | setHasComplianceExport(Boolean hasComplianceExport) |
| `Icon` | [`ObjsIcon`](../../doc/models/objs-icon.md) | Required | - | ObjsIcon getIcon() | setIcon(ObjsIcon icon) |
| `Id` | `String` | Required | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` | String getId() | setId(String id) |
| `IsAssigned` | `Boolean` | Optional | - | Boolean getIsAssigned() | setIsAssigned(Boolean isAssigned) |
| `IsEnterprise` | `Integer` | Optional | - | Integer getIsEnterprise() | setIsEnterprise(Integer isEnterprise) |
| `IsOverStorageLimit` | `Boolean` | Optional | - | Boolean getIsOverStorageLimit() | setIsOverStorageLimit(Boolean isOverStorageLimit) |
| `LimitTs` | `Integer` | Optional | - | Integer getLimitTs() | setLimitTs(Integer limitTs) |
| `Locale` | `String` | Optional | - | String getLocale() | setLocale(String locale) |
| `MessagesCount` | `Integer` | Optional | - | Integer getMessagesCount() | setMessagesCount(Integer messagesCount) |
| `MsgEditWindowMins` | `Integer` | Optional | - | Integer getMsgEditWindowMins() | setMsgEditWindowMins(Integer msgEditWindowMins) |
| `Name` | `String` | Required | - | String getName() | setName(String name) |
| `OverIntegrationsLimit` | `Boolean` | Optional | - | Boolean getOverIntegrationsLimit() | setOverIntegrationsLimit(Boolean overIntegrationsLimit) |
| `OverStorageLimit` | `Boolean` | Optional | - | Boolean getOverStorageLimit() | setOverStorageLimit(Boolean overStorageLimit) |
| `PayProdCur` | `String` | Optional | - | String getPayProdCur() | setPayProdCur(String payProdCur) |
| `Plan` | [`Plan`](../../doc/models/plan.md) | Optional | - | Plan getPlan() | setPlan(Plan plan) |
| `PrimaryOwner` | [`ObjsPrimaryOwner`](../../doc/models/objs-primary-owner.md) | Optional | - | ObjsPrimaryOwner getPrimaryOwner() | setPrimaryOwner(ObjsPrimaryOwner primaryOwner) |
| `SsoProvider` | [`SsoProvider`](../../doc/models/sso-provider.md) | Optional | - | SsoProvider getSsoProvider() | setSsoProvider(SsoProvider ssoProvider) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "archived": false,
  "avatar_base_url": "avatar_base_url4",
  "created": 18,
  "date_create": 124,
  "deleted": false,
  "domain": "domain0",
  "email_domain": "email_domain4",
  "icon": {
    "image_102": "image_1020",
    "image_132": "image_1326",
    "image_230": "image_2308",
    "image_34": "image_340",
    "image_44": "image_440",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "id": "id4",
  "name": "name4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

