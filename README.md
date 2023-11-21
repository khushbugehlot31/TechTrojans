import random

class BiometricSystem:
    def verify_fingerprint(self, fingerprint):
        # Simulated biometric verification
        return random.choice([True, False])

class VotingMachine:
    def __init__(self, biometric_system):
        self.biometric_system = biometric_system
        self.registered_voters = {}

    def register_voter(self, voter_id, fingerprint):
        self.registered_voters[voter_id] = fingerprint

    def vote(self, voter_id, candidate):
        if voter_id in self.registered_voters:
            fingerprint = self.registered_voters[voter_id]
            if self.biometric_system.verify_fingerprint(fingerprint):
                print(f"Voter {voter_id} verified. Vote cast for {candidate}.")
            else:
                print(f"Biometric verification failed for voter {voter_id}. Vote not cast.")
                
        else:
            print(f"Voter {voter_id} is not registered. Vote not cast.")

