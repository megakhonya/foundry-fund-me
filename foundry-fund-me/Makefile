-include .env

# Clean the repo
clean:; forge clean

# Remove modules
remove:; rm -rf .gitmodules && rm -rf .git/modules/* && rm -rf lib && touch .gitmodules && git add . && git commit -m "modules"

install :; forge install cyfrin/foundry-devops@0.2.2 --no-commit && forge install smartcontractkit/chainlink-brownie-contracts@1.1.1 --no-commit && forge install foundry-rs/forge-std@v1.8.2 --no-commit

# Update Dependencies

# Update Dependencies
update:; forge update

# Build
build:; forge build

# Test
test:; forge test

# Snapshot
snapshot:; forge snapshot

# Format
format:; forge fmt

# Run Anvil
anvil:; anvil -m 'test test test test test test test test test test test junk' --steps-tracing --block-time 1

# Deploy to Sepolia
deploy-sepolia:
	forge script script/DeployFundMe.s.sol:DeployFundMe --rpc-url $(SEPOLIA_RPC_URL) \
	--private-key $(PRIVATE_KEY) \
	--broadcast \
	--verify \
	--etherscan-api-key $(ETHERSCAN_API_KEY) \
	-vvvv

	