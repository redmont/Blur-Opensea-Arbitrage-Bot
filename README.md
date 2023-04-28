# NFT MEV :robot:

...to extract it, starting with ar₿$.

## To-do :clipboard:

- [x] `getNfts`
  - [x] getBlurSlugs
  - [x] getBlurSales & save to `SALES`
  - [ ] getOsBids & save to `BIDS`
- [ ] `bot` (recheck)
  - [ ] Listen to subOrders
  - [ ] If new bid, check `SALES`
  - [ ] If new sale, check `BIDS`
  - [ ] Connect to the exec arb
- [ ] `subOrders`
  - [ ] Get `BLUR_SALES`
    - [x] If `SALE` `contractAddress` exists in database, add to database.
    - [ ] If `SALE` `contractAddress` does not exist in database:
      - [x] Add to database
      - [ ] Get corresponding `OS_BIDS` via API and save to database `BIDS`
  - [ ] Get `OS_BIDS` (via stream)
    - [ ] If `contractAddress` exists in `SALES` (collected during `getNfts` and `subOrders`), add to `BIDS`
    - (Current implementation adds all bids)
- [ ] Consider: price & addr formatting for db
- [ ] Consider: `subOrders` Blur Sales does not add traits
- [ ] Setup database on `vps0`
  - [ ] Allow transferring data for `vps1` via SSH
- [ ] Cleaner
  - [ ] Remove expired data from database


## Commands :
1st terminal inside bot-nft/api-blur:
`yarn rebuild && node .`

2nd terminal, run Mongo (with stream support):
`sudo mongod --port 27017 --dbpath /var/lib/mongodb --replSet rs0 --bind_ip localhost`

3rd terminal, Mongodb UI:
`robo3t`


## Git Commit Types :construction_worker:

- :sparkles: `feat`: A new feature
- :bug: `fix`: A bug fix
- :books: `docs`: Documentation changes
- :art: `style`: Changes that do not affect the meaning of the code (e.g. formatting, missing semi-colons, etc.)
- :recycle: `refactor`: Code changes that neither fix a bug nor add a feature
- :arrow_up: `chore`: Changes to the build process, dependencies, or other non-code related changes
- :white_check_mark: `test`: Adding or modifying tests
- :globe_with_meridians: `i18n`: Internationalization/localization changes
- :construction: `WIP`: Work in progress (not intended for the final release)
- :x: `revert`: Reverting a previous commit

Let's go! :muscle: