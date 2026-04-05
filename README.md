<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:1E3258,100:137DC5&height=220&section=header&text=IIC%20%E2%80%94%20Intent-Integrity%20Chain&fontSize=42&fontColor=FFD700&fontAlignY=35&desc=Cerrando%20la%20brecha%20entre%20intenci%C3%B3n%20y%20c%C3%B3digo&descSize=18&descColor=ffffff&descAlignY=55" alt="IIC Banner" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/versión-2.7.16-137DC5?style=for-the-badge" alt="Versión" />
  <img src="https://img.shields.io/badge/licencia-GPL--3.0-122562?style=for-the-badge" alt="Licencia" />
  <img src="https://img.shields.io/badge/pipeline-8%20pasos-FFD700?style=for-the-badge" alt="Pipeline" />
  <img src="https://img.shields.io/badge/plataformas-4-BBA0CC?style=for-the-badge" alt="Plataformas" />
</p>

---

## Acerca de IIC

**IIC (Intent-Integrity Chain)** es un kit de herramientas que preserva la intención del desarrollador desde la idea hasta la implementación. Genera Architecture Decision Records con verificación criptográfica en cada paso, asegurando que lo que se especificó es exactamente lo que se construyó.

Compatible con múltiples asistentes de código IA: Claude Code, Codex, Gemini y OpenCode.

---

## Características principales

- **Pipeline de 8 pasos (specify → implement)** — Flujo completo desde especificación hasta implementación
- **Verificación de integridad por paso** — Hash SHA256 encadenado en cada transición
- **ADR automatizados** — Architecture Decision Records generados y trazados automáticamente
- **Compatible multi-plataforma** — Claude Code, OpenAI Codex, Google Gemini y OpenCode
- **Dashboard interactivo** — Kanban estático HTML con badges de clarificación y cadena BDD
- **Trazabilidad completa de decisiones** — Cadena ininterrumpida de intención a código

---

## Instalación

Agrega IIC como plugin de Claude Code o úsalo como herramienta standalone:

```bash
# Instalar vía Tessl
tessl install tessl-labs/intent-integrity-kit

# O clonar localmente
git clone https://github.com/JaviMontano/mao-iic.git
cd mao-iic
```

---

## Pipeline de integridad

```
Intención --> Spec --> .feature --> Steps --> Código
          |        |            |          |
          |        |            |          +-- calidad de steps verificada
          |        |            +------------- hash bloqueado (sin manipulación)
          |        +-------------------------- tags @FR-XXX trazados
          +----------------------------------- clarificado hasta alineado
```

**Principio clave**: Ninguna parte de la cadena se valida a sí misma. Los archivos `.feature` se bloquean antes de la implementación. Las step definitions se verifican por cobertura y calidad.

---

## Uso rápido

```
/iikit-00-constitution     # Gobernanza del proyecto (agnóstico a tecnología)
/iikit-01-specify          # Especificación de features (QUÉ, no CÓMO)
/iikit-02-plan             # Plan técnico (CÓMO - frameworks, stack)
/iikit-03-checklist        # Checklists de calidad
/iikit-04-testify          # Archivos Gherkin .feature desde requisitos
/iikit-05-tasks            # Descomposición en tareas
/iikit-06-analyze          # Verificación de consistencia cross-artefacto
/iikit-07-implement        # Ejecución con verificación de integridad
/iikit-08-taskstoissues    # Exportar a GitHub Issues
/iikit-clarify             # Resolver ambigüedades (cualquier artefacto, cualquier momento)
```

---

## Cadena de verificación BDD

El núcleo de IIC es prevenir la verificación circular — donde la IA modifica tests para que coincidan con código defectuoso.

1. `/iikit-04-testify` genera archivos Gherkin `.feature` desde los escenarios de la spec
2. Un hash SHA256 de todas las líneas de steps se almacena en `context.json`
3. `/iikit-07-implement` aplica la cadena BDD completa antes de marcar cualquier tarea:
   - **Verificación de hash** — archivos `.feature` sin alterar desde testify
   - **Cobertura de steps** — todos los pasos Gherkin tienen step definitions
   - **Fase RED** — los tests deben fallar antes de escribir código de producción
   - **Fase GREEN** — los tests deben pasar después de escribir código de producción
   - **Calidad de steps** — sin cuerpos vacíos, sin `assert True`, sin assertions faltantes

---

## Compatibilidad

| Plataforma | Soporte |
|------------|---------|
| Claude Code | Completo (plugin nativo) |
| OpenAI Codex | Compatible vía CLI |
| Google Gemini | Compatible vía adaptador |
| OpenCode | Compatible vía CLI |

---

## Parte del Ecosistema MetodologIA / JM Labs

IIC se integra con otros componentes del ecosistema:

| Repositorio | Descripción |
|-------------|-------------|
| [mao-sdd](https://github.com/JaviMontano/mao-sdd) | Specification-Driven Development para software |
| [mao-discovery-framework](https://github.com/JaviMontano/mao-discovery-framework) | Framework de discovery y análisis organizacional |
| [mao-sovereign-architect](https://github.com/JaviMontano/mao-sovereign-architect) | Arquitectura de software con agentes autónomos |

---

## Licencia

Este proyecto está licenciado bajo **GPL-3.0**. Consulta el archivo [LICENSE](LICENSE) para más detalles.

---

<p align="center">
  Creado por <a href="https://github.com/JaviMontano">Javier Montaño</a> · MetodologIA · GPL-3.0
</p>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:1E3258,100:137DC5&height=120&section=footer" alt="Footer" />
</p>
