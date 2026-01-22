# Azure-Lab-06-PIM-JIT

# 🧪Lab 06: Gestión de Privilegios Just-In-Time (PIM) – Aprobación + Auditoría

## 🎯 Objetivo
Eliminar administradores permanentes y reducir la superficie de ataque mediante **Privileged Identity Management (PIM)**:
- Asignaciones **Eligible (JIT)** en lugar de permanentes
- Activación temporal con **justificación**
- (Opcional/Pro) Flujo de **aprobación** y evidencia en **auditoría**

## 🧰 Requisitos
- Microsoft Entra ID con **PIM habilitado** (Identity Governance).
- Usuarios de laboratorio (ej.: `usuario_4` como candidato a la activación).

## 🛠️ Tareas realizadas (paso a paso)
1. **Asignar rol “User Administrator” como Eligible** a `usuario_4`.
2. **Endurecer la activación** del rol con:
   - Duración máxima: **1 hora**
   - Requerir **Azure MFA**
   - Requerir **justificación**
   - Requerir **aprobación** para activar
3. **Activar el rol** desde `My roles` con `usuario_4` indicando motivo.
4. **Aprobar la solicitud** (aprobador) y verificar que la activación se concede.
5. **Validar auditoría**: evidenciar evento **Succeeded** de activación PIM.

**01 – Eligible assignment creado**


[<img src="images/01-eligible.png" width="800">](images/01-eligible.png)

**02 – Role settings (MFA + Justificación + Approval + 1h)**


[<img src="images/role-settings-approval.png" width="800">](images/role-settings-approval.png)

**03 – Auditoría: Eligible assignment (Succeeded)**


[<img src="images/03-audit-eligible-assignment-user4.png" width="800">](images/03-audit-eligible-assignment-user4.png)

**04 – Solicitud de activación (My roles → Activate)**


[<img src="images/04-activate-form-justification.png" width="800">](images/04-activate-form-justification.png)

**05 – Aprobación / Activación concedida**


[<img src="images/05-activation-active.png" width="800">](images/05-activation-active.png)

**06 – Auditoría: Activación completada (Succeeded)**


[<img src="images/03-audit-activation.png" width="800">](images/03-audit-activation.png)


## ✅ Checklist de verificación
- [x] El rol se asigna como **Eligible**, no como Active permanente.
- [x] La activación está limitada en tiempo (**máx. 1h**).
- [x] La activación requiere **Azure MFA**.
- [x] La activación requiere **justificación**.
- [x] La activación requiere **aprobación**.
- [x] Existe evidencia en **Audit logs** con estado **Succeeded**.

## 🧠 Aprendizajes clave
- PIM permite **privilegios bajo demanda (JIT)**, reduciendo el riesgo de cuentas con permisos permanentes.
- Con aprobación y justificación, la elevación queda **controlada y trazable**, útil para cumplimiento y auditorías.

## 🗣️ Qué le diría a un cliente / en entrevista
“Con PIM evito administradores permanentes: los usuarios quedan **Eligible** y solo elevan privilegios cuando lo necesitan, por tiempo limitado y con **MFA + justificación + aprobación**. Además, todo queda registrado en **auditoría**, lo que mejora seguridad y cumplimiento.”
