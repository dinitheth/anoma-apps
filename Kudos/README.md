# Scale-Free Kudos

Status: DRAFT

## Interface

### Instantiate

Instantiate a quantity of a Kudos kind and assign it to a specified owner.

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
