# Create only the data you need

## Rules

- Build only the records and attributes required for the behavior under test.
- Avoid heavy, full-graph fixtures that hide intent.
- Prefer focused factories or inline setup over global data.

## Bad example

```ruby
let(:user) { create(:user, :with_profile, :with_subscription, :with_team) }
let!(:teams) { create_list(:team, 5, :with_members) }
```

## Good example

```ruby
let(:user) { create(:user, role: 'admin') }
```
