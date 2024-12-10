# Co-noir standalone starter

A simple [Noir](https://noir-lang.org/docs/) project that gets executed with [co-noir](https://github.com/TaceoLabs/co-snarks/tree/main/co-noir/co-noir).

## Installations

### Noir

Co-noir `0.3.0` works with Noir `1.0.0-beta.0` (which itself needs `bb` version `0.63.0`). Get correct versions of `nargo` and `bb`: 

```bash
$ noirup --version 1.0.0-beta.0
$ bbup --v 0.63.0
```

### Co-noir

Install co-noir from source:

```bash
$ git clone https://github.com/TaceoLabs/co-snarks/tree/main
$ cd co-snarks/co-noir/co-noir
$ cargo install --path .
```

Check the installation:

```bash
$ co-noir --version
# co-noir 0.3.0
```

#### Examples in co-noir

Note that in the repository of co-snarks you can find many co-noir sample projects in `co-snarks/co-noir/co-noir/examples/test_vectors`. These can be executed with the scripts in `co-snarks/co-noir/co-noir/examples`. This project uses all of the same config, data and script style as those examples. 

## Run full flow

The script will execute the following steps:
- compile nargo project
- split the `Prover.toml` input into shares
- generate witnesses using MPC
- prove using MPC
- create verification key
- verify proof

```bash
$ ./run_full_mpc_flow.sh
```

You can also execute these steps manually. For the MPC related steps make sure to execute them in parallel in different consoles (because they need to communicate amongst each other).