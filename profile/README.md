# TC-Program-Integration

The TC-Program-Integration team builds Power Platform and Dataverse tooling and integration work. Our focus is XrmToolBox plugins and Dataverse developer workflows, supported by integration projects that connect organizational data to Dataverse solutions.

## XrmToolBox plugins

Each plugin lives in its own repository, with its own history, issues and releases. The [XrmToolBoxPlugins](https://github.com/TC-Program-Integration/XrmToolBoxPlugins) repository links them together as git submodules and holds the shared build script.

| Plugin | Repository | What it does |
|---|---|---|
| WebResourcesManager | [WebResourcesManager](https://github.com/TC-Program-Integration/WebResourcesManager) | Our feature fork of MsCrmTools Web Resources Manager: refresh, push, compare and watch links between web resources and local files, dev/test-only push. |
| FlowsAsCode | [FlowsAsCode](https://github.com/TC-Program-Integration/FlowsAsCode) | Edit Power Automate cloud-flow JSON (solution flows) as local files, with links, compare, build-before-push and a Runs tab. |
| CommandButtons | [CommandButtons](https://github.com/TC-Program-Integration/CommandButtons) | Create and configure model-driven command bar buttons. |
| OrgChartManagerSync | [OrgChartManagerSync](https://github.com/TC-Program-Integration/OrgChartManagerSync) | Set each user's manager from the OrgChart (saved chart or plan CSV). Read-only preview, pick rows, then apply to a dev/test environment only. |
| SolutionDelta | [SolutionDelta](https://github.com/TC-Program-Integration/SolutionDelta) | Push the forms and views changed in a pac-unpacked solution folder to a dev/test environment, then publish their tables. No solution import. |
| SchemaAsCode | [SchemaAsCode](https://github.com/TC-Program-Integration/SchemaAsCode) | Create and update Dataverse tables, columns, choices, status reasons, relationships and keys from a TypeScript schema (`dist/schema.json`) in a dev/test environment. Deletes only after confirmation. |
| XrmTools.UI | [XrmTools.UI](https://github.com/TC-Program-Integration/XrmTools.UI) | Shared WinForms UI kit (theme, guidance banner, notices, dialogs, environment prompt) compiled into the plugins. |

## Power Platform and integration projects

| Repository | What it is |
|---|---|
| [Power-Platform-Starter](https://github.com/TC-Program-Integration/Power-Platform-Starter) | React starter for model-driven app web resources and Power Automate flows, in TypeScript and Python, with tests that run without Dataverse. |
| [TAN-BDN](https://github.com/TC-Program-Integration/TAN-BDN) | The TAN/BDN request dialog (React) on the Event Plan, Training Item and Operational Plan forms, and the acting sync flow. Built on the Power Platform starter. |
| [TAN-BDN-Form---Andrew-Changes](https://github.com/TC-Program-Integration/TAN-BDN-Form---Andrew-Changes) | Variant of the Power Platform starter for the TAN/BDN form changes. |
| [orgchart-sync](https://github.com/TC-Program-Integration/orgchart-sync) | Reads the Transport Canada OrgChart, matches people to Dataverse users, and writes the manager plan that the OrgChartManagerSync plugin applies. Never writes to Dataverse. |

## Getting started

### Plugins

```powershell
git clone --recurse-submodules https://github.com/TC-Program-Integration/XrmToolBoxPlugins.git
# already cloned without the plugins?
git submodule update --init
```

Built plugin files are not kept in git. Get them from a plugin's Releases page, or build them with the shared build script.

Plugins in private repositories are not updated by XrmToolBox's public Tool Library. Run `Launch-XrmToolBox.cmd` from XrmToolBoxPlugins instead of XrmToolBox directly: it checks the private repositories for updates before XrmToolBox starts.

### Power Platform projects

Start from Power-Platform-Starter. On Windows 10 or 11, run `setup.cmd` in the project folder. It installs the tools into your user folder and needs no administrator rights. Then run `pnpm dev` for preview, docs and tests together, and `pnpm check` for the checks CI runs.

## Working here

- All work lives in this organization. New repositories are created here.
- A plugin change is made in the plugin's own repository. Then update the pinned commit in XrmToolBoxPlugins.
- The repositories are private and require organization membership to view.

## Questions and issues

Open an issue in the repository the question is about. For questions that span several plugins, use XrmToolBoxPlugins.

---

Maintained by the TC-Program-Integration team.
