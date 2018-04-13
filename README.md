# Modification

Added extra logic for select (left join and right outer join).

    {
        "where": {
            "foo": "bar"
        },
        "leftJoin": {
            "relationName": {
                "relatedModelPropName": "value"
            }
        }
    }

SQL generated will look somthing like this:

    SELECT 
        Model."id",
        Model."foo"
    FROM
        "public"."model" AS Model
    LEFT JOIN
        "public"."relatedModel" AS RelatedModel ON RelatedModel."dependsOfRelationTypeAndForeignKey" = Model."dependsOfRelationTypeAndForeignKey"
    WHERE
        Model."foo" = "bar" AND RelatedModel."relatedModelPropName" = "value"
    GROUP BY
        Model."id"


# LoopBack Connector

LoopBack Connector is a set of building blocks simplifying implementation
of datasource-specific connectors like Oracle, MongoDB, REST.

**For full documentation, see the official StrongLoop documentation**:
 * [Data sources and connectors](http://docs.strongloop.com/display/public/LB/Database+connectors)

## Installation

    npm install loopback-connector

## Usage

See [loopback-connector-mysql](https://github.com/strongloop/loopback-connector-mysql) 
for an example of connector using this module.

