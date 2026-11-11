# Andeshandbook para Claude

Explora montañas, rutas de ascenso y senderos de trekking con el catálogo y la
comunidad de [Andeshandbook](https://www.andeshandbook.org/).
Publicador: Sociedad Geográfica de Documentación Andina.

El plugin conecta con `https://api.andeshandbook.org/mcp`. Permite consultar
fichas, fotografías, experiencias y productos de la tienda cuando la consulta
lo requiere. El contenido disponible depende de la cuenta conectada.
La información publicada no confirma las condiciones actuales del terreno,
el clima, los accesos ni la seguridad de una actividad.

## Instalación

### Claude

En Personalizar → Plugins, usa la opción de cargar un plugin personalizado e
importa el ZIP del plugin. Completa la conexión OAuth de Andeshandbook cuando
Claude la solicite. La disponibilidad depende del plan y de las políticas de
la organización. Consulta la [guía de Claude](https://support.claude.com/en/articles/13837440-use-plugins-in-claude).

### Claude Code desde este repositorio

Una vez publicado el contenido en
[andeshandbook/claude](https://github.com/andeshandbook/claude), ejecuta:

```sh
claude plugin marketplace add https://github.com/andeshandbook/claude.git
claude plugin install andeshandbook@andeshandbook
```

Para probar una copia local, usa `claude plugin marketplace add .` desde su raíz.
Inicia Claude Code, abre `/mcp` y autentica la conexión de Andeshandbook.
OAuth descubre y registra el cliente; no necesitas copiar un secreto ni un token.

## Ejemplos

- «Quiero descubrir rutas de trekking de una jornada cerca de Santiago».
- «¿Qué rutas publicadas tiene el Volcán Osorno y qué datos debo comparar?».
- «Muéstrame fotografías de una montaña con sus créditos».

El servicio es de lectura: no publica aportes, envía mensajes, reserva guías ni
crea carritos, pedidos o pagos. Las compras ocurren en la
[tienda](https://tienda.andeshandbook.org/).

## Estructura y comprobación

`.claude-plugin/marketplace.json` registra el plugin de `plugins/andeshandbook`.
Su manifiesto está en `.claude-plugin/plugin.json` y su conexión en `.mcp.json`.
Las instrucciones y herramientas vigentes se reciben del servidor MCP.

Con Claude Code v2.1.281 o posterior puedes comprobar ambos manifiestos:

```sh
claude plugin validate .
claude plugin validate ./plugins/andeshandbook
```

La versión del paquete es independiente de la versión del servidor MCP.
La instalación, OAuth y consultas reales en Claude requieren un ensayo con una
cuenta; validar estos archivos no acredita ese ensayo ni aprobación de Anthropic.

[Soporte](https://www.andeshandbook.org/home/faq) ·
[Términos y privacidad](https://www.andeshandbook.org/home/terminos_y_condiciones)
