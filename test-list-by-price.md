# Comandos curl para probar el endpoint list-by-price

## Endpoint implementado
`GET /api/v1/integration/cli2/products/list-by-price`

## 4 casos de prueba:

### 1. Ambos parámetros (start-price y end-price)
```bash
curl -X GET "http://localhost:8080/api/v1/integration/cli2/products/list-by-price?start-price=10&end-price=20" \
     -H "Accept: application/json"
```

### 2. Solo start-price (precio mínimo)
```bash
curl -X GET "http://localhost:8080/api/v1/integration/cli2/products/list-by-price?start-price=10" \
     -H "Accept: application/json"
```

### 3. Solo end-price (precio máximo)
```bash
curl -X GET "http://localhost:8080/api/v1/integration/cli2/products/list-by-price?end-price=20" \
     -H "Accept: application/json"
```

### 4. Sin parámetros (todos los productos)
```bash
curl -X GET "http://localhost:8080/api/v1/integration/cli2/products/list-by-price" \
     -H "Accept: application/json"
```

## Nota:
- Los productos se devuelven ordenados por precio ascendente
- Todos los casos devuelven productos del tipo ProductCli2 completos
- El perfil 'cli2' debe estar activo para que funcione el endpoint