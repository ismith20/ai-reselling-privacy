---
title: Privacy Policy — AI Reselling Ecosystem
---

# AI Reselling Ecosystem — Privacy Policy

**Effective date:** November 21, 2026  
**Last updated:** November 22, 2026

## Who operates this application

AI Reselling Ecosystem is a privately operated inventory and resale-management project. It is independent of eBay Inc. Its eBay integration is intended to help the authorized seller track orders, organize cards and other inventory, and manage packaging and shipping tasks.

## What information the application accesses

If the seller authorizes eBay access, the application may retrieve order details through the official eBay Sell Fulfillment API. eBay's response can contain order IDs, listing/item IDs, payment and fulfillment status, quantities, shipment deadlines, and buyer-related information.

The current local order tracker is designed to store only information needed for its tasks: **order ID, eBay item ID, payment/fulfillment status, item quantity, ship-by date where available, inventory identifiers and storage locations, and task/alert status.** The current tracker is not designed to store buyers' names, postal addresses, phone numbers, or email addresses. Information received from eBay may be processed temporarily in memory without being added to its local database.

The seller may separately enter an item description, physical storage location, and related inventory information.

## Purposes of use

The application uses the data to:

- Match eBay orders to the seller's inventory.
- Create a packaging and shipping task list and avoid duplicate sale alerts.
- Track locally marked packaging progress and eBay-reported fulfillment status.
- Produce local order summaries and, if the seller explicitly installs the optional Windows scheduled task, poll orders every five minutes and display generic local Windows notifications for new paid sales and a daily task report.

The current code **does not** automatically publish listings, make purchases, place bids, change listing prices, mark orders shipped on eBay, or relist items. Windows-local scheduled monitoring is opt-in and does not forward data to outside notification services. Planned external ZEUS/StarNet notifications and listing recommendations are not active unless separately deployed and configured.

## Storage and security

The application is designed to run primarily on the seller's own Windows computer. Operational records, alert-delivery status and daily report state are kept in a **local SQLite database**. A privacy-reduced local JSON task feed and daily report may be stored under the application's ignored local output directory; these include order IDs and inventory task details but not buyer names or addresses. The seller OAuth integration is designed to protect access and refresh tokens using **Windows Data Protection API (DPAPI)** tied to the operator's Windows account.

Application secrets, OAuth tokens, unredacted order responses, and local databases are not intended to be committed to public GitHub repositories. Access to locally stored data depends on the security of the operator's computer and account. No method of data storage is completely risk-free.

## Service providers and sharing

eBay supplies information to the application under the seller's authorization. The application **does not sell personal information** or use eBay order information for third-party advertising.

A future ZEUS/StarNet workflow may receive a restricted task summary containing order IDs, item IDs, operational status and inventory locations. That feed is designed to omit buyer names and contact and shipping-address details. If the seller enables an external AI model or notification provider, the data sent to that provider will be subject to its own terms and privacy practices. **External ZEUS delivery and phone push are not connected in the current prototype.** Optional notifications use generic messages on the operator's own Windows desktop.

## Retention, access, and deletion

Local order and inventory records are retained on the operator's device until the operator deletes them or implements a separate retention policy. Currently, there is no automatic deletion schedule for those local records.

The seller can revoke the application's access through eBay's authorized application controls. Revocation stops future authorized API access but does not automatically remove data already stored locally. To remove existing local data, the operator must also delete the applicable local records or files. Applicable eBay developer obligations, including required account-deletion handling, must be followed when relevant.

## Changes to this policy

The application may change during development. This policy will be updated if its use, collection, storage or sharing of information materially changes. The latest public version will be maintained in this repository.

## Contact

For **general, non-sensitive** questions about this privacy policy, use the [public GitHub Issues page](https://github.com/ismith20/ai-reselling-privacy/issues).

**Do not publish passwords, OAuth tokens, order IDs, account details, buyer information, postal addresses or other sensitive personal information in a public GitHub issue.** For a request involving private data, first request a private method of contact without disclosing the data publicly.

---

This policy describes the current and proposed behavior of the independently operated AI Reselling Ecosystem; it is not eBay's Privacy Notice.
