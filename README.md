1const { JsonRpcProvider } = require("ethers");

// Base Mainnet RPC URL
const BASE_RPC_URL = "https://mainnet.base.org";

async function connectToBase() {
    try {
        // 1. Initialize the provider
        const provider = new JsonRpcProvider(BASE_RPC_URL);

        // 2. Test the connection (get current block number)
        const blockNumber = await provider.getBlockNumber();
        
        console.log("Successfully connected to Base Network!");
        console.log(`Current Block Number: ${blockNumber}`);

        // 3. Optional: Get network details
        const network = await provider.getNetwork();
        console.log(`Chain ID: ${network.chainId}`);

    } catch (error) {
        console.error("Connection failed:", error);
    }
}

connectToBase();
