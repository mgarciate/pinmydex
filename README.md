## First approach

There will be a DAO created with a SC. In this DAO there are 3 main agents:

- Proposers: proposers will have the power to propose dappnode packages to be pinned, ideal proposer profiles are developers and projects interested in have a dappnode package in the dappstore propertly pinned. Proposers will have to stake in the SC, the amount to be staked will deppend on the package size. The higher the more expensive.

  - Actions:
    - Propose content + stake + pin-time. To calculate the stake, ideally the size should be calculatd by the SC. stake amount deppends on of the size of the hash provided and the time.
    - Renew?
  - Reactions:
    - If propose suceed, then burn the stake.
    - If propose not suceed, then return stake less a fee for the DAO.

- Voters: these agents will be able to vote content to be pinned. The votes should define the IPFS hash to be pinned and the time. Once this time expires, it could be under a new votation.

  - Actions:
    - Vote hashes to be pinned
    - Vote trusted ipfs peers to be added
    - Vote trusted ipfs peers to be removed
      - Set new ipfs_cluster secret in order to remove peers

- Pinners: pinners can be classified in two subsections: followers and trusted peers (see IPFS dir for more info). This agent will be in charge of pinning the dappnode packages. There will be used a trusted pool of peers for pinning the content, this is necessary because determine wheter or not a content is pinned so pinners can be rewarded, is hard to implement.
  - It will have private + public key
  - Actions
    - GET content to be pinned in string array format
    - GET secret_cluster + subscribe secret change
    - GET/DELETE(own)/POST(own) peerstore: https://cluster.ipfs.io/documentation/deployment/setup/ . The peerstore must have 1 peer address per pinner

Each role will be part of an economy system that can burn NODE for pinning content in the benefit of dappnode users and projects that want to be part of dappnode.

## Develop

In order to achieve the above approach, there will be needed

- [ ] SC for the DAO
- [ ] UI to interact with the SC
- [ ] IPFS:
  - [ ] Ipfs trusted pool
  - [ ] Ipfs follower
