# A Simple Counter application

Status: DRAFT

## Interface

### Initialize

Create a counter type with an initial value.

### Update

Update the value of an existing counter.

## Logic

### Initialize

The value of the counter must be 0.

### Update

The types of the counter before and after must be equal. The value of the counter must be incremented by 1.

## How to run it

You need:

* A copy of the latest [juvix nightly build](https://github.com/anoma/juvix-nightly-builds/releases/tag/nightly-2024-06-07-0.6.2-ce938ef)

* A clone of [anoma](https://github.com/anoma/anoma) checked out at branch: `paul/juvix-resource-test`

Then:

* Compile the `SimpleCounter.juvix` with Juvix: `juvix compile anoma SimpleCounter.juvix`

* Copy the output file `SimpleCounter.nockma` to the root of the Anoma clone you made in the previous step: `cp SimpleCounter.nockma $PATH_TO_ANOMA_CLONE/RawCounterTransaction.nockma`

* Run the test that verifies the transaction in Anoma: `mix test test/resource_test.exs:218`
