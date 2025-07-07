# Cases API - Todo List

**Priority:** HIGH (Core functionality)  
**Complexity:** MODERATE  
**Current Status:** 18/18 endpoints completed (100% complete)

## ✅ Completed Tools (18/18)
- [x] `get_case` - Get case details (GET /cases/{caseID}) - ✅ **IMPLEMENTED** in `src/tools/cases/get-case.js`
- [x] `create_case` - Creates new case (POST /cases) - ✅ **IMPLEMENTED** in `src/tools/cases/create-case.js`
- [x] `delete_case` - Delete case in create stage (DELETE /cases/{caseID}) - ✅ **IMPLEMENTED** in `src/tools/cases/delete-case.js`
- [x] `get_case_view` - Get view details for a case (GET /cases/{caseID}/views/{viewID}) - ✅ **IMPLEMENTED** in `src/tools/cases/get-case-view.js`
- [x] `get_case_stages` - Get case stages list (GET /cases/{caseID}/stages) - ✅ **IMPLEMENTED** in `src/tools/cases/get-case-stages.js`
- [x] `get_case_ancestors` - Get ancestor case hierarchy (GET /cases/{caseID}/ancestors) - ✅ **IMPLEMENTED** in `src/tools/cases/get-case-ancestors.js`
- [x] `get_case_descendants` - Get descendant case hierarchy (GET /cases/{caseID}/descendants) - ✅ **IMPLEMENTED** in `src/tools/cases/get-case-descendants.js`
- [x] `get_case_action` - Get case action details (GET /cases/{caseID}/actions/{actionID}) - ✅ **IMPLEMENTED** in `src/tools/cases/get-case-action.js`
- [x] `perform_case_action` - Perform case action (PATCH /cases/{caseID}/actions/{actionID}) - ✅ **IMPLEMENTED** in `src/tools/cases/perform-case-action.js`
- [x] `perform_bulk_action` - Perform bulk action (PATCH /cases) - ✅ **IMPLEMENTED** in `src/tools/cases/perform-bulk-action.js`
- [x] `bulk_cases_patch` - Alternative bulk cases implementation (PATCH /cases) - ✅ **IMPLEMENTED** in `src/tools/cases/bulk-cases-patch.js`
- [x] `change_to_next_stage` - Change to next stage (POST /cases/{caseID}/stages/next) - ✅ **IMPLEMENTED** in `src/tools/cases/change-to-next-stage.js`
- [x] `change_to_stage` - Change to specified stage (PUT /cases/{caseID}/stages/{stageID}) - ✅ **IMPLEMENTED** in `src/tools/cases/change-to-stage.js`
- [x] `recalculate_case_action_fields` - Recalculate calculated fields & whens for case action (PATCH /cases/{caseID}/actions/{actionID}/recalculate) - ✅ **IMPLEMENTED** in `src/tools/cases/recalculate-case-action-fields.js`
- [x] `refresh_case_action` - Refresh case action form data with updated values (PATCH /cases/{caseID}/actions/{actionID}/refresh) - ✅ **IMPLEMENTED** in `src/tools/cases/refresh-case-action.js`
- [x] `get_case_view_calculated_fields` - Get calculated fields for case view (POST /cases/{caseID}/views/{viewID}/calculated_fields) - ✅ **IMPLEMENTED** in `src/tools/cases/get-case-view-calculated-fields.js`
- [x] `release_case_lock` - Release pessimistic lock on case (DELETE /cases/{caseID}/updates) - ✅ **IMPLEMENTED** in `src/tools/cases/release-case-lock.js`

## ✅ Related Completed Tools (Case Types - 2/2) ✅ COMPLETE
- [x] `get_case_types` - List available case types (GET /casetypes) - ✅ **IMPLEMENTED** in `src/tools/casetypes/get-case-types.js`
- [x] `get_case_type_bulk_action` - Get bulk action metadata (GET /casetypes/{caseTypeID}/actions/{actionID}) - ✅ **IMPLEMENTED** in `src/tools/casetypes/get-case-type-bulk-action.js`

## ✅ Core Infrastructure
- [x] `ping_pega_service` - Test OAuth2 connectivity - ✅ **IMPLEMENTED** in `src/tools/ping-service.js`

## ✅ High Priority (Core Operations) ✅ COMPLETE
- [x] `perform_case_action` - Perform case action (PATCH /cases/{caseID}/actions/{actionID}) - ✅ **IMPLEMENTED** in `src/tools/cases/perform-case-action.js`

## ✅ Medium Priority (Advanced Operations) ✅ COMPLETE
- [x] `get_case_ancestors` - Get ancestor case hierarchy (GET /cases/{caseID}/ancestors) - ✅ **IMPLEMENTED** in `src/tools/cases/get-case-ancestors.js`
- [x] `get_case_descendants` - Get descendant case hierarchy (GET /cases/{caseID}/descendants) - ✅ **IMPLEMENTED** in `src/tools/cases/get-case-descendants.js`
- [x] `change_to_next_stage` - Change to next stage (POST /cases/{caseID}/stages/next) - ✅ **IMPLEMENTED** in `src/tools/cases/change-to-next-stage.js`
- [x] `change_to_stage` - Change to specified stage (PUT /cases/{caseID}/stages/{stageID}) - ✅ **IMPLEMENTED** in `src/tools/cases/change-to-stage.js`
- [x] `release_case_lock` - Release lock (DELETE /cases/{caseID}/updates) - ✅ **IMPLEMENTED** in `src/tools/cases/release-case-lock.js`

## 🔄 Advanced Priority (Specialized Operations)
- [ ] `get_bulk_actions` - Get bulk actions (POST /cases/bulk-actions)
- [x] `perform_bulk_action` - Perform bulk action (PATCH /cases) - ✅ **IMPLEMENTED** in `src/tools/cases/perform-bulk-action.js`
- [x] `add_optional_process` - Add optional process (POST /cases/{caseID}/processes/{processID}) - ✅ **IMPLEMENTED** in `src/tools/cases/add-optional-process.js`
- [x] `recalculate_case_fields` - Recalculate calculated fields (PATCH /cases/{caseID}/actions/{actionID}/recalculate) - ✅ **IMPLEMENTED** as `recalculate_case_action_fields` in `src/tools/cases/recalculate-case-action-fields.js`
- [x] `refresh_case_action` - Refresh case action (PATCH /cases/{caseID}/actions/{actionID}/refresh) - ✅ **IMPLEMENTED** in `src/tools/cases/refresh-case-action.js`
- [x] `get_calculated_fields` - Get calculated fields for case view (POST /cases/{caseID}/views/{viewID}/calculated_fields) - ✅ **IMPLEMENTED** as `get_case_view_calculated_fields` in `src/tools/cases/get-case-view-calculated-fields.js`
- [ ] `refresh_case_view` - Refresh view details (PATCH /cases/{caseID}/views/{viewID}/refresh)

## Implementation Notes
- **Dependencies:** PegaAPIClient, OAuth2Client
- **Common Parameters:** caseID (URL encoded), actionID, viewID, stageID
- **Error Handling:** 404 (case not found), 401 (unauthorized), 400 (bad request)
- **Testing:** Each tool needs corresponding test file in /tests/
- **Pattern:** Follow GetCaseTool and CreateCaseTool implementation patterns

## MCP Tool Names Convention
- Prefix: No prefix needed (e.g., `get_case`, not `pega_get_case`)
- Format: snake_case
- Descriptive: Action + target (e.g., `perform_case_action`, `get_case_stages`)
