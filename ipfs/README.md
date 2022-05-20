## Architecture

The architecture will be composed by:

- Trusted pool of ipfs nodes: this pool will read the ipfs hashes to be pinned from the SC.

- Ipfs cluster followers: these followers can join the collaborative pool of nodes and contribute by pinning content. Ideally all dappnodes running IPFS local should join as follower for their own benefit.

> ipfs-cluster-follow helps running IPFS Cluster follower peers.

> Follower peers subscribe to a Cluster controlled by a set of "trusted
> peers". They collaborate in pinning items as dictated by the trusted peers and
> do not have the power to make Cluster-wide modifications to the pinset.

> Follower peers cannot access information nor trigger actions in other peers.

- There will be a list of RPC to get the hashes to pin. This RPC is chosen randomly every single time, this will increase the security of deppending on just one peer

- The remote configuration used to start the ipfs cluster daemon can be served by an endpoint. Ideally the configuration items must be defined by the SC and be on chain

## DOCS

- Config cluster: https://cluster.ipfs.io/documentation/reference/configuration/
