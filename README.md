# powerwall-dashboard-mcp
Quick and easy docker container that creates a MCP server that connects to the default influxdb 1.8 of the [Powerwall Dashboard project](https://github.com/jasonacox/Powerwall-Dashboard). This allows you to use your AI/Agent of choice to ask it various questions about your Tesla Powerwall and/or solar system. See example questions and answers below.

**AI Disclaimer:** Yes, I used AI to create this. Use at your own risk!

```bash 
    git clone https://github.com/ampersandru/powerwall-dashboard-mcp.git
    cd powerwall-dashboard-mcp
    docker compose up -d --build
```


The MCP server should be accessible by `http://<server-ip>:8765/mcp`
You can add this to Hermes, OpenwebUI, Claude, etc. If you are exposing to the public, be sure to set the `MCP_AUTH_TOKEN` env variable in the docker-compose

**Example questions and responses** (all via Hermes with Qwen3.8-27B IQ4_KS ik_llama)

After feeding Hermes PGE historic rates as a memory, I had it guestimate my current ROI:
<img width="722" height="745" alt="image" src="https://github.com/user-attachments/assets/89dfcd12-0e8e-4f7a-bbb2-bc2bdf2607d0" />

Asking Hermes to compare past 3 Mays and what the correlation to generation was:
<img width="728" height="968" alt="image" src="https://github.com/user-attachments/assets/cbd2e0f2-c22f-4d2f-874a-fa4d0999ff9e" />

Asking Hermes if buying a Powerwall was worth it (yes, but long ROI on NEM2, doesnt take in account outages)
<img width="739" height="995" alt="image" src="https://github.com/user-attachments/assets/5ffedf68-19d5-4122-abef-040eeafea748" />

Fed Hermes the exact dates and cost of cleanings to pull from PWD (via hermes connected to my Discord):
<img width="896" height="659" alt="image" src="https://github.com/user-attachments/assets/5b31bd56-4c69-4db0-b187-da7e30580cff" />

Hermes even used its own script to output a graph outlining it all:
<img width="1540" height="1155" alt="image" src="https://github.com/user-attachments/assets/73756179-ab10-44ab-9460-f3913dcee21b" />
