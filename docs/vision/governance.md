# Governance

DropIt will delegate its governance control to the open governance system of the Polkadot Network.

This is the same model as system parachains like the Asset Hub.

## Bootstrapping Governance

The DropIt chain will initially deploy with the [Sudo pallet](https://github.com/paritytech/polkadot-sdk/tree/master/substrate/frame/sudo) to simplify the initial bootstrapping phase of the network.

Once the network is ready, it will ask Polkadot's OpenGov to take control of the network through a runtime upgrade, removing the Sudo pallet and empowering Polkadot to govern it.
