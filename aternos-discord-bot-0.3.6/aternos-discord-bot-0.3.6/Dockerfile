FROM golang:1.18-alpine

WORKDIR /app

# expose available environment variables
ENV DISCORD_TOKEN="MTUwODg1ODE2MzQ0Mzc5ODAyNg.GW0nVM.3JUrgRckN4ZrFauYtw3ArrlkAqEje16RTBVGw8"
ENV ATERNOS_SESSION="0xCeFrLMYyhAvqeXt8OinH1qe3cjE3zO5uG3mWyhbd351Pa4E1jouQxc8RN55lsCGwmdKtTau4mhzIXdwskWQZAfrPXYtD9TIBQp"
ENV ATERNOS_SERVER="3qf1OMXcNrxgTRIH"
ENV MONGO_DB_URI=""
ENV PROXY=""

# install dependencies
COPY go.mod ./
COPY go.sum ./
RUN go mod download

# copy files
COPY . ./

# build binary
RUN go build -o ./bin/aternos-discord-bot ./cmd/main.go

CMD [ "./bin/aternos-discord-bot" ]
