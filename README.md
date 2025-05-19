# omr_autofill 

Prefill OMR Sheets with data automatically!

### Configuration

The omr template should be saved under `omr_template.pdf` file name and must be placed in the root directory. (WIP Library API and CLI) and config file must be saved under `config.json` file. 

Please refer [config.md](./config.md) for the full config spec. 

### Building and running 

The project can be build with the following command: 

```
npm run build
```

The script can then be run with 

```
npm run generate
```

### Note

Library API, CLI and Config generator  is work in progress and will be implemented soon. 
For existing config generation please open an issue at https://github.com/KittyBorgX/omr_autofill/issues and provide the OMR template file.