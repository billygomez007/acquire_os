# Release Process
PR -> CI checks -> security review for authorization/AI/tool/payment modifications -> staging deployment -> QA and smoke tests -> release approval -> production deploy -> monitor and rollback path. No direct production secrets in source. Record migration, environment, feature flags, approval owner, recovery steps and rollback outcome.
