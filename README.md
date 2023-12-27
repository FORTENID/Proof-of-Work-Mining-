# Proof-of-Work-Mining-
Implementing a basic proof-of-work algorithm for mining blocks
import hashlib

def proof_of_work(last_proof):
    proof = 0
    while not valid_proof(last_proof, proof):
        proof += 1
    return proof

def valid_proof(last_proof, proof):
    guess = f'{last_proof}{proof}'.encode()
    guess_hash = hashlib.sha256(guess).hexdigest()
    return guess_hash[:4] == "0000"

# Example usage
last_proof = 123
new_proof = proof_of_work(last_proof)
