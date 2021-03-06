**@substrate/txwrapper**

> [README](../README.md) / [Globals](../globals.md) / "src/methods/proxy/announce"

# Module: "src/methods/proxy/announce"

## Index

### Interfaces

* [ProxyAnnounceArgs](../interfaces/_src_methods_proxy_announce_.proxyannounceargs.md)

### Functions

* [announce](_src_methods_proxy_announce_.md#announce)

## Functions

### announce

▸ **announce**(`args`: [ProxyAnnounceArgs](../interfaces/_src_methods_proxy_announce_.proxyannounceargs.md), `info`: [BaseTxInfo](../interfaces/_src_util_types_.basetxinfo.md), `options`: [OptionsWithMeta](../interfaces/_src_util_types_.optionswithmeta.md)): [UnsignedTransaction](../interfaces/_src_util_types_.unsignedtransaction.md)

*Defined in [src/methods/proxy/announce.ts:40](https://github.com/paritytech/txwrapper/blob/ddb0953/src/methods/proxy/announce.ts#L40)*

Publish the hash of a proxy-call that will be made in the future.

This must be called `ProxyDefinition.delay` blocks before the corresponding
`proxy` is attempted if the delay associated with the proxy relationship is
greater than zero. When a `ProxyDefinition.delay` is 0 `announce` is not neccesary
and `proxy` can be called at any time.

No more than `MaxPending` announcements may be made at any one time. On Kusama and Polkadot
`MaxPending` is set to 32.

This will take a deposit of `AnnouncementDepositFactor` as well as
`AnnouncementDepositBase` if there are no other pending announcements.

The dispatch origin for this call must be _Signed_ and a proxy of `real`.

#### Parameters:

Name | Type | Description |
------ | ------ | ------ |
`args` | [ProxyAnnounceArgs](../interfaces/_src_methods_proxy_announce_.proxyannounceargs.md) | Arguments specific to this method. |
`info` | [BaseTxInfo](../interfaces/_src_util_types_.basetxinfo.md) | Information required to construct the transaction. |
`options` | [OptionsWithMeta](../interfaces/_src_util_types_.optionswithmeta.md) | Registry and metadata used for constructing the method.  |

**Returns:** [UnsignedTransaction](../interfaces/_src_util_types_.unsignedtransaction.md)
