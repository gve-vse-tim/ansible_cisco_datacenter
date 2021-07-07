# Lessons Learned

## Nesting roles within the collection

When structuring groups of roles into a common heirarchy, such as:

- roles/nxos/vlans
- roles/nxos/vpc

There is no inheritance of **defaults** or **meta** from the parent group
level.  As such, directories like the following are ignored:

- roles/nxos/meta
- roles/nxos/defaults

The defaults and meta must be replication in each complete sub-role.
