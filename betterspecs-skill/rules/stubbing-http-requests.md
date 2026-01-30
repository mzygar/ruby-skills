# Stubbing HTTP requests

## Rules

- Stub external HTTP requests in specs.
- Use WebMock for simple stubbing and VCR for recording real interactions.
- Keep recorded cassettes small and focused on the behavior under test.

## Bad example

```ruby
it 'fetches profile data' do
  client.fetch_profile('https://api.example.com/user/1')
  # Hits the real network in test.
end
```

## Good example

```ruby
stub_request(:get, 'https://api.example.com/user/1')
  .to_return(status: 200, body: '{"name":"Ada"}')

it 'fetches profile data' do
  expect(client.fetch_profile('https://api.example.com/user/1')).to eq('Ada')
end
```
