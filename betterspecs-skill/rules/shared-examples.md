# Shared examples

## Rules

- Use `shared_examples` to remove duplication across specs.
- Keep shared examples small and focused on a behavior.
- Pass parameters to shared examples to keep them reusable.

## Bad example

```ruby
describe '#admin?' do
  context 'when admin' do
    it { expect(subject.admin?).to eq(true) }
  end
end

describe '#manager?' do
  context 'when manager' do
    it { expect(subject.manager?).to eq(true) }
  end
end
```

## Good example

```ruby
shared_examples 'a role checker' do |method|
  it { expect(subject.public_send(method)).to eq(true) }
end

describe '#admin?' do
  it_behaves_like 'a role checker', :admin?
end

describe '#manager?' do
  it_behaves_like 'a role checker', :manager?
end
```
