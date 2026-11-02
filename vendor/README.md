# vendor

`gilrs` 0.11.2 and `gilrs-core` 0.6.8 as published on crates.io (Apache-2.0
or MIT, https://gitlab.com/gilrs-project/gilrs), used through the workspace's
`[patch.crates-io]`, with one addition: `MacGamepadExt::location_id`, a Mac
gamepad's IOKit location ID (`gilrs-core/src/lib.rs`,
`gilrs-core/src/platform/macos/gamepad.rs`, `gilrs/src/gamepad.rs`,
`gilrs/src/lib.rs`; each marked "eqoa-rust-client-vanilla").

On a Mac gilrs numbers the gamepads in the order the process found them, and
macOS hands a process the ones already connected in no set order: two game
windows could number two identical controllers each the other way round, and
both read the same one while multiboxing. The location ID is the same in every
process, so `input::Gamepads` names a Mac's controllers by it.

To move to a newer gilrs, copy the new versions here and add the four
additions again.
