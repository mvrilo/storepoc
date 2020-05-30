# storepoc

`storepoc` is a SOA project built with Go intended to serve as a PoC and boilerplate for future development. It's built around DDD with gorm, protobuf, grpc and rest (via grpc-gateway and gin). The entrypoint is located at the root of the project, the `main.go`.

The business logic is located at the `core` directory. Each component of our server there, or _services_, must implement an interface for being loaded in the main server:

```
type RegisterableService interface {
	Register(s *Server) error
}
```

Our services are defined and loaded at the main entrypoint, before starting the server.

For configuration, check `pkg/config`.


## installing

With Go:

```
go get github.com/mvrilo/storepoc
```

Building, with go:

```
git clone github.com/mvrilo/storepoc
cd storepoce
make deps
make
```

With docker-compose:

`docker-compose up`


## author

Murilo Santana <<mvrilo@gmail.com>>