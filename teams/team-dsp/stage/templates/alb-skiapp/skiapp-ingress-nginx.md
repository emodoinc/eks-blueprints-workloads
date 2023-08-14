apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: skiapp-ingress-nginx
  namespace: team-riker
spec:
  ingressClassName: nginx
  rules:
    - host: 
      http:
        paths:
          - path: /
            pathType: Prefix
            backend:
              service:
                name: skiapp-service
                port:
                  number: 80
