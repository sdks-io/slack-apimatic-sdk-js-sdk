
# Team Object

*This model accepts additional fields of type unknown.*

## Structure

`TeamObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `archived` | `boolean \| undefined` | Optional | - |
| `avatarBaseUrl` | `string \| undefined` | Optional | - |
| `created` | `number \| undefined` | Optional | - |
| `dateCreate` | `number \| undefined` | Optional | - |
| `deleted` | `boolean \| undefined` | Optional | - |
| `description` | `string \| null \| undefined` | Optional | - |
| `discoverable` | `unknown \| undefined` | Optional | - |
| `domain` | `string` | Required | - |
| `emailDomain` | `string` | Required | - |
| `enterpriseId` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^[E][A-Z0-9]{8,}$` |
| `enterpriseName` | `string \| undefined` | Optional | - |
| `externalOrgMigrations` | [`ExternalOrgMigrations \| undefined`](../../doc/models/external-org-migrations.md) | Optional | - |
| `hasComplianceExport` | `boolean \| undefined` | Optional | - |
| `icon` | [`ObjsIcon`](../../doc/models/objs-icon.md) | Required | - |
| `id` | `string` | Required | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` |
| `isAssigned` | `boolean \| undefined` | Optional | - |
| `isEnterprise` | `number \| undefined` | Optional | - |
| `isOverStorageLimit` | `boolean \| undefined` | Optional | - |
| `limitTs` | `number \| undefined` | Optional | - |
| `locale` | `string \| undefined` | Optional | - |
| `messagesCount` | `number \| undefined` | Optional | - |
| `msgEditWindowMins` | `number \| undefined` | Optional | - |
| `name` | `string` | Required | - |
| `overIntegrationsLimit` | `boolean \| undefined` | Optional | - |
| `overStorageLimit` | `boolean \| undefined` | Optional | - |
| `payProdCur` | `string \| undefined` | Optional | - |
| `plan` | [`Plan \| undefined`](../../doc/models/plan.md) | Optional | - |
| `primaryOwner` | [`ObjsPrimaryOwner \| undefined`](../../doc/models/objs-primary-owner.md) | Optional | - |
| `ssoProvider` | [`SsoProvider \| undefined`](../../doc/models/sso-provider.md) | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

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

