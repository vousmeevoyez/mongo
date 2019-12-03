## start replica set without auth
go into one of container and access mongo shell
use this replica set config
config = {
	"_id": "mongo-rs",
	"members": [{
	"_id": 0,
	"host": "accessible-ip:27019"
	}, {
	"_id": 1,
	"host": "accessible-ip:27020"
	}]
}

rs.initiate(config)

## start replica set with auth
start just one container without replica set and key file
go into one of container and access mongo shell
create user with root permission
start all other container including the one we set before with replica set and keyfile
use this replica set config
config = {
	"_id": "mongo-rs",
	"members": [{
	"_id": 0,
	"host": "accessible-ip:27019"
	}, {
	"_id": 1,
	"host": "accessible-ip:27020"
	}]
}

rs.initiate(config)
