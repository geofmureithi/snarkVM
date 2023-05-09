# Making snarkVm enclave compatible

## Suggested approach
1. Create a new crate eg `snarkvm-enclave`
2. Carefully setup the deps, and include some features eg `synthesizer` and `console`
3. To import the enclave compatible snarkVm then one can use `snarkvm-enclave = { ... features=['synthesizer'] }`

## Breakdown by crate's support of sgx enclave

| Crate      | Default Features | No Default Features |
| ----------- | ----------- |-----------|
| Algorithims      | ✗ (1)       | ✓	
| Circuit   | ✗ (1)         | ✗ (2)	
| Console   | ✗ (1)         | ✓	
| Curves   | ✓         | ✗ (3)	
| Fields   | ✓          | ✗	
| Parameters   | ✗ (1)         | ✓	
| r1cs   |    ✓     | ✓	
| Synthesizer   | ✗ (1)         | ✗	
| Utilities   | ✓         | ✗	
| VM   | ✗ (1)         | ✗ (4)
| Wasm   | ✗ (1)         | ✓	

# Additional notes

CI should be set for the new crate to allow checking if things are broken in the `sgx` target. 



