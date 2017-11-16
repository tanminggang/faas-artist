## Get faas-cli
```
curl -sSL https://cli.openfaas.com | sudo sh
```

## Build and deploy
```
faas-cli build -f artist.yml
faas-cli deploy -f artist.yml
```

## Profit!

### Generates Monet style

![Original](/artist/input/blizzard.jpg?raw=true "Original Blizzard")
![Styled](/styled/blizzard-styled-monet.jpg?raw=true "Monet style 1")

```
curl -X POST -H X-style-name:monet -H X-style-index:1 \
  --data-binary @artist/input/blizzard.jpg "http://localhost:8080/function/artist" > blizzard-styled-monet.jpg
```

### Generates Varied style
![Original](/artist/input/vespa-faas.jpg?raw=true "Original Vespa and Faas")
![Styled](/styled/vespa-faas-varied-24.jpg?raw=true "Varied style 24")

```
curl -X POST -H X-style-name:varied -H X-style-index:24 \
  --data-binary @artist/input/vespa-faas.jpg "http://localhost:8080/function/artist" > vespa-faas-varied-24.jpg
```