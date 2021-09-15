# Kitty Pallet Design

## Calls
- fn create_kitty
- fn breed_kitty
  - first_parent: KittyId
  - second_parent: KittyId
- fn transfer_kitty
  - recipient: AccountId
  - kitty_id: KittyId
- fn sell_kitty
  - kitty_id: KittyId
  - price: Balance

## Types
- struct Kitty
  - owner: AccountId
  - dna: u128
  - gender: char
  - for_sale: bool
  - price: Balance


## Storage
- Kitties: double_map AccountId, u32 => Option<Kitty>
- NextKittyId: KittyId

## Events
- KittyCreated
  - kitty_id: KittyId
  - kitty: Kitty
- KittyBred
  - first_parent: AcccountId
  - second_parent: AccountId
  - kity: Kitty
- KittyTransfered
  - sender: AccountId
  - recipient: AccountId
  - kitty_id: KittyId
- KittySold
  - kitty_id: KittyId
