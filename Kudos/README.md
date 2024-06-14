# Scale-Free Kudos

Status: DRAFT

## Paricipants

### Originator

A user that can create any quantity of a particular kind of Kudos.

### Owner

A user that owns some quantity of a particular kind of Kudos.

## Resource Structure

### Label

The value of the `label` field is the _originator_'s public key.

### Data

The value of the `data` field consists of:

* The _originator signature_ - A signature generated from the resource kind using the _originator_'s private key
* The _owner_'s public key

## Transaction Structure

### Extra

The value of the `extra` field is a signature generated from the transaction commitments and nullifiers using the _owner_'s private key.

## Interface

### Instantiate

Instantiate a quantity of a Kudos kind owned by a specified owner.

See [Example.juvix](Example.juvix) for an example of using this interface. 

## Logic

### Instantiate

All resources must be signed by the _originator_ i.e:
* The _originator signature_ must be valid for the _resource kind_ using the _originator public key_.

All consumed resources must be authorized for by the _owner_ i.e:
* The _transaction signature_ must be valid for the transaction commitments and nullifiers using the _owner public key_.

## How to run it

You need:

* A copy of the latest [juvix nightly build](https://github.com/anoma/juvix-nightly-builds/releases/latest)

* A clone of [anoma](https://github.com/anoma/anoma) checked out at branch: `paul/juvix-resource-test`

Then:

* Compile the `Example.juvix` with Juvix: `juvix compile anoma Example.juvix`

* Copy the output file `Example.nockma` to the root of the Anoma clone you made in the previous step: `cp Example.nockma $PATH_TO_ANOMA_CLONE/RawCounterTransaction.nockma`

* Run the test that verifies the transaction in Anoma: `mix test test/resource_test.exs:218`
