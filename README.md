# Demo MCP Server

[![smithery badge](https://smithery.ai/badge/@j03rul4nd/mcp-001)](https://smithery.ai/server/@j03rul4nd/mcp-001)

Este proyecto implementa un servidor MCP (Model Context Protocol) utilizando el SDK de MCP. El servidor incluye herramientas y recursos dinámicos que pueden ser utilizados para realizar operaciones específicas y generar respuestas dinámicas.

## Características

- **Herramienta de suma**: Una herramienta que toma dos números como entrada y devuelve su suma.
- **Recurso de saludo dinámico**: Un recurso que genera un saludo personalizado basado en el nombre proporcionado en la URI.

## Requisitos previos

- Node.js (versión 16 o superior)
- npm (gestor de paquetes de Node.js)


## Instalación

### Installing via Smithery

To install Demo MCP Server for Claude Desktop automatically via [Smithery](https://smithery.ai/server/@j03rul4nd/mcp-001):

```bash
npx -y @smithery/cli install @j03rul4nd/mcp-001 --client claude
```

### Manual Installation

1. Clona este repositorio:
   ```bash
   git clone <URL-del-repositorio>
   cd mcp_001
   ```

2. Instala las dependencias necesarias:
   ```bash
   npm install
   ```

## Uso

1. Inicia el servidor MCP:
   ```bash
   node serverMCP.ts
   ```

2. El servidor comenzará a escuchar mensajes en la entrada estándar (stdin) y enviará respuestas a la salida estándar (stdout).

## Estructura del proyecto

- `serverMCP.ts`: Archivo principal que configura y ejecuta el servidor MCP.
- `package.json`: Archivo de configuración del proyecto que incluye las dependencias y scripts.

## Ejemplos de uso

### Herramienta de suma
Envía un mensaje al servidor con el siguiente formato para sumar dos números:
```json
{
  "tool": "add",
  "params": {
    "a": 5,
    "b": 3
  }
}
```
Respuesta esperada:
```json
{
  "content": [
    { "type": "text", "text": "8" }
  ]
}
```

### Recurso de saludo dinámico
Accede al recurso de saludo utilizando una URI como `greeting://John` para obtener un saludo personalizado:
```json
{
  "resource": "greeting://John"
}
```
Respuesta esperada:
```json
{
  "contents": [
    {
      "uri": "greeting://John",
      "text": "Hello, John!"
    }
  ]
}
```

## Licencia

Este proyecto está bajo la licencia MIT. Consulta el archivo `LICENSE` para más detalles.
