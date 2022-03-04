.PHONY: credentials
credentials:
	# Set PostgreSQL credentials
	vault kv get -format json -field data kv/backstage | jq -c '{stringData:{"POSTGRES_USER": "backstage", "POSTGRES_PASSWORD": "secret"}}' | kubectl --namespace backstage patch secret postgres-secrets --patch-file /dev/stdin

.PHONY: bootstrap
bootstrap: credentials
