# Major Themes

v1.5...

## K8s Version Support

## Upgrade Guides

## Breaking Changes

### Ceph

- Ceph mons require an odd number for a healthy quorum. An even number of mons is now disallowed.
- Update deprecated CRD apiextensions.k8s.io/v1beta1 to v1 ([#6424](https://github.com/rook/rook/pull/6424))
- preservePoolsOnDelete is deprecated for CephFilesystem and is no longer allowed because of data-loss concerns. preserveFilesystemOnDelete acts as a replacement and preserves the filesystem when the CephFilesystem CRD is deleted (which implicitly includes all associated pools). See [#6495](https://github.com/rook/rook/pull/6495) for more details.
- The discovery daemon is disabled by default since the discovery is not necessary in most clusters. Enable the discovery daemon if
  devices are being added to nodes and you want to automatically configure OSDs on new devices without restarting the operator.

## Features

### Ceph

* Stretch clusters for mons and OSDs to work reliably across two datacenters (Experimental mode)
* Ceph Block Pool: add mirroring support
* Ceph Block Pool: add `replicasPerFailureDomain` to set the number of replica in a failure domain ([#5591](https://github.com/rook/rook/issues/5591))
* Ceph Cluster: export the storage capacity of the ceph cluster ([#6475](https://github.com/rook/rook/pull/6475))
* Ceph Cluster: add encryption support with Key Management Service
