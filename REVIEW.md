# REVIEW NOTES

- Rebase on master
- Move ex_sni, ex_dbus into elixir-desktop and update mix.exs to point to the new locations
- Remove meta files: .editorconfig  .vscode and line-length customization
- Use existing `somecall(variable = %{match pattern})` instead of `somecall(%{match pattern} = variable)`
- __proxy.ex__: This is hardcoding app logic from the sample app: `menu = try_module_func(mod, :handle_info, [:changed, menu], menu)`. I don't see a way to keep the behaviour without a real GenServer, so:
    - use GenServer directly: Remove `server.ex` and `proxy.ex` modules, reduce complexity.
- Fix double translation from :wx => Adapter.Wx and :dbus => Adapter.Dbus
- Remove the Adapters.ex, just call `adapter.update_dom(...)` directly. This is no external extension point.

