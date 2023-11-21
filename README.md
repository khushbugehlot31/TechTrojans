import random

class BiometricSystem:
    def verify_fingerprint(Self, fingerprint):
        # Simulated biometric verification
        return random.choice([True, False])

class VoterMachine:
    def __init__(Self, biometric_system):
        self.biometric_system = biometric_system
        self.registered_voters = {}

    def register_voter(Self, voter_id, fingerprint):
        self.registered_voters[voter_id] = fingerprint

    def vote(Self, voter_id, candidate):
        if voter_id in self.registered_voters:
            fingerprint = self.registered_voters[voter_id]
            if self.biometric_system.verify_fingerprint(fingerprint):
                print(f"Voter {voter_id} verified. Vote cast for {candidate}.")
            else:
                print(f"Biometric verification failed for voter {voter_id}. Vote not cast.")
                
        else:
            print(f"Voter {voter_id} is not registered. Vote not cast.")

