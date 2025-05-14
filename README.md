# fumo

## Project Tasks

- [ ] Prepare clean Blender collection archive ([#12](https://github.com/M3-org/fumo/issues/12))
- [ ] Define asset naming, hierarchy, and transform conventions ([#11](https://github.com/M3-org/fumo/issues/11))
- [ ] Add expression controls ([#10](https://github.com/M3-org/fumo/issues/10))
- [ ] Fabric and stitching materials ([#9](https://github.com/M3-org/fumo/issues/9))
- [ ] Rig base model and traits for VRM and Unity compatibility ([#8](https://github.com/M3-org/fumo/issues/8))
- [ ] UV cleanup / layout improvements ([#7](https://github.com/M3-org/fumo/issues/7))
- [ ] Create expression set ([#6](https://github.com/M3-org/fumo/issues/6))
- [ ] Standardize shader and material setup for glTF and VRM ([#5](https://github.com/M3-org/fumo/issues/5))
- [ ] Define modelling task list ([#4](https://github.com/M3-org/fumo/issues/4))
- [ ] Determine which traits can be reused ([#3](https://github.com/M3-org/fumo/issues/3))
- [ ] Determine texture-only variant traits ([#2](https://github.com/M3-org/fumo/issues/2))
- [ ] Remake base model ([#1](https://github.com/M3-org/fumo/issues/1))

## Sprint Plan Kanban (Beta)

```mermaid
---
config:
  kanban:
    ticketBaseUrl: 'https://github.com/M3-org/fumo/issues/'
---
kanban
  %% Sprint 1: Base Model, Asset Pipeline, Rigging & Material Standards
  section Sprint 1
  todo[To Do]
    %% Tasks for madjin
    issue11[#11 Define asset naming...]@{ ticket: '11', priority: 'Medium', assigned: 'madjin' }
    issue4[#4 Define modelling task list]@{ ticket: '4', priority: 'Medium', assigned: 'madjin' }
    issue3[#3 Determine which traits can be reused]@{ ticket: '3', priority: 'Medium', assigned: 'madjin' }
    issue2[#2 Determine texture-only variant traits]@{ ticket: '2', priority: 'Medium', assigned: 'madjin' }
    %% Tasks for Vianvolaeus (or to be assigned)
    issue1[#1 Remake base model]@{ ticket: '1', priority: 'High' }
    issue9[#9 Fabric and stitching materials]@{ ticket: '9', priority: 'High' }
    issue5[#5 Standardize shader and material setup...]@{ ticket: '5', priority: 'High' }
    issue7[#7 UV cleanup / layout improvements]@{ ticket: '7', priority: 'Medium' }
    %% Shared Tasks
    issue8[#8 Rig base model and traits...]@{ ticket: '8', priority: 'High' }
  inprogress[In Progress]
  done[Done]

  %% Sprint 2: Expressions & Further Modeling (Placeholder)
  section Sprint 2
  todo2[To Do (Sprint 2)]
    issue6[#6 Create expression set]@{ ticket: '6', priority: 'Medium' }
    issue10[#10 Add expression controls]@{ ticket: '10', priority: 'Medium' }
  inprogress2[In Progress (Sprint 2)]
  done2[Done (Sprint 2)]

  %% Sprint 3: Packaging & Final QA (Placeholder)
  section Sprint 3
  todo3[To Do (Sprint 3)]
    issue12[#12 Prepare clean Blender collection archive]@{ ticket: '12', priority: 'Medium' }
  inprogress3[In Progress (Sprint 3)]
  done3[Done (Sprint 3)]