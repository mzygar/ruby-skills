# Test what you see

## Rules

- Emphasize request/feature/integration specs that cover full behavior.
- Keep controller specs light; focus on behavior rather than implementation.
- Use Capybara (or similar) when verifying user-visible behavior.

## Bad example

```ruby
describe UsersController, type: :controller do
  it 'assigns @users' do
    get :index
    expect(assigns(:users)).to be_present
  end
end
```

## Good example

```ruby
feature 'Users list' do
  scenario 'shows users' do
    create(:user, name: 'Ada')
    visit '/users'
    expect(page).to have_content('Ada')
  end
end
```
