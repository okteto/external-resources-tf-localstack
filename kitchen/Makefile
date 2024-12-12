# Variables
IP_ADDRESS := 127.0.0.1
HOSTNAME := localstack

.PHONY: start
start:
	go run main.go

.PHONY: debug
debug:
	dlv debug --headless --listen=:2345 --log --api-version=2

.PHONY: add-host
add-host:
	@if grep -q "$(IP_ADDRESS) $(HOSTNAME)" /etc/hosts; then \
		echo "Entry already exists: $(IP_ADDRESS) $(HOSTNAME)"; \
	else \
		echo "Updating /etc/hosts"; \
		echo "$(IP_ADDRESS) $(HOSTNAME)" | sudo tee -a /etc/hosts; \
		echo "/etc/hosts updated"; \
	fi

.PHONY: remove-host
remove-host:
	@if [ -z "$(IP_ADDRESS)" ] || [ -z "$(HOSTNAME)" ]; then \
		echo "Error: Both IP_ADDRESS and HOSTNAME must be provided"; \
		exit 1; \
	fi
	@if grep -q "$(IP_ADDRESS) $(HOSTNAME)" /etc/hosts; then \
		echo "Restoring /etc/hosts"; \
		sudo sed -i.bak "/^$(IP_ADDRESS) $(HOSTNAME)$$/d" /etc/hosts; \
		echo "/etc/hosts restored"; \
	else \
		echo "Entry not found: $(IP_ADDRESS) $(HOSTNAME)"; \
	fi